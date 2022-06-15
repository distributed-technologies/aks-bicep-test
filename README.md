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
