# Helm in OCI test

This test was done by spinning up an ACR, then creating an admin token, with which I pushed a [podinfo chart](https://github.com/stefanprodan/podinfo/tree/master/charts/podinfo) to the ACR using [this](https://helm.sh/blog/storing-charts-in-oci/) guide from helm.

I then followed Flux's own [guide](https://fluxcd.io/docs/guides/helmreleases/#helm-oci-repository) on how to deploy a helm release from an OCI,
using their guide on how to [apply secrets](https://fluxcd.io/docs/guides/helmreleases/#helm-repository-authentication-with-credentials) I got this deployment to work.


By following these guides I was able to deploy podinfo on a kind cluster using ACR as a helm repository.

TL:DR it works
