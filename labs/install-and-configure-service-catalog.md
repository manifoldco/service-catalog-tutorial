# Install and configure service-catalog

Install [Helm][helm] into your Kubernetes cluster, and configure it to be able
to find service-catalog:

```bash
helm init
helm repo add svc-cat https://svc-catalog-charts.storage.googleapis.com
```

Grant Helm permission to admin your cluster, so it can install service-catalog:

```
kubectl create clusterrolebinding tiller-cluster-admin \
    --clusterrole=cluster-admin \
    --serviceaccount=kube-system:default
```

Install service-catalog:

```
helm install svc-cat/catalog --version 0.1.3 --name catalog --namespace catalog
```

*More detailed instructions for installing service-catalog can be found in the
service-catalog github repo [here][svccat-install].*

<br>

**Next:** [Configure the Manifold service broker](configure-the-manifold-service-broker.md)

[helm]: https://helm.sh/
[svccat-install]: https://github.com/kubernetes-incubator/service-catalog/blob/master/docs/install.md
