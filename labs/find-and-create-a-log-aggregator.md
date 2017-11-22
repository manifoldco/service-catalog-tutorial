# Find and create a log aggregator

Search for a service that provides logging:

```bash
kubectl get clusterserviceclass \
-o custom-columns=Name:{.spec.externalName},\
ID:{.metadata.name},\
Description:{.spec.description} \
| grep log
```
```
logdna                 234qkjvrptpy3thna4qttwt7m2nf6   The best logging service you will ever use
```

Find a free plan for the service:

```bash
kubectl get clusterserviceplans \
-o custom-columns=Name:{.spec.externalName},\
ID:{.metadata.name},\
Service\ ID:{.spec.clusterServiceClassRef.name},\
Free:{.spec.free} \
--sort-by=spec.clusterServiceClassRef.name \
| grep 234qkjvrptpy3thna4qttwt7m2nf6 | grep true
```
```
quaco             23558gd5kaw5z462e3mvaknj5veuj   234qkjvrptpy3thna4qttwt7m2nf6   true
```

## Create a service instance and binding

Create a LogDNA [service instance][osbterm] and [binding][osbterm]. This will
create a  LogDNA account for you through [Manifold][manifold] using the quaco free plan:

```bash
kubectl apply -f - <<EOF
apiVersion: servicecatalog.k8s.io/v1beta1
kind: ServiceInstance
metadata:
  name: tutorial-logdna
spec:
  clusterServiceClassExternalName: logdna
  clusterServicePlanExternalName: quaco
EOF
```
```bash
kubectl apply -f - <<EOF
apiVersion: servicecatalog.k8s.io/v1beta1
kind: ServiceBinding
metadata:
  name: tutorial-logdna-binding
spec:
  instanceRef:
    name: tutorial-logdna
EOF
```

The service binding will create a [secret][secret] holding configuration values
for the service:

```bash
kubectl describe secret tutorial-logdna-binding
```

```
Name:         tutorial-logdna-binding
Namespace:    default
Labels:       <none>
Annotations:  <none>

Type:  Opaque

Data
====
RESOURCE_ID:  29 bytes
ACCOUNT:      10 bytes
KEY:          32 bytes
```

<br>

**Next:** [Use the log aggregator](use-the-log-aggregator.md)

[osbterm]: https://github.com/openservicebrokerapi/servicebroker/blob/v2.13/spec.md#terminology
[manifold]: https://www.manifold.co
[secret]: https://kubernetes.io/docs/concepts/configuration/secret/
