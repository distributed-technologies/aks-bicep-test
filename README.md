# aks-bicep-test

This is for testing a preview aks pipeline

# flux install

```sh
flux bootstrap github \
  --owner=my-github-username \
  --repository=my-repository \
  --path=clusters/my-cluster \
  --personal
```

```sh
flux bootstrap github \
  --owner=distributed-technologies \
  --repository=aks-bicep-test \
  --branch=monitoring-stack \
  --path=clusters/aks \
  --personal \
  --token-auth
```

# Ceph dual default storage class quick fix

``` bash
kubectl patch storageclass default -p '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"false"}}}'
```


# Access ceph dashboard

From https://github.com/rook/rook/issues/2526#issuecomment-487363346

``` bash
kubectl proxy
```

Then go to `http://localhost:8001/api/v1/namespaces/rook-ceph/services/https:rook-ceph-mgr-dashboard:https-dashboard/proxy/` in your browser

get the credentials with
```
kubectl -n rook-ceph get secret rook-ceph-dashboard-password -o jsonpath="{['data']['password']}" | base64 --decode && echo
```
