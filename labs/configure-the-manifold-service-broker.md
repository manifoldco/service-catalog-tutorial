# Configure the Manifold service broker

Create a [Manifold] API token:

```bash
manifold tokens create
```

Answer the prompts. Be sure to grant `write` access for your token:

```
✔ Token Description: service-catalog tutorial token
✔ write
Token              ████████████████████████████████████████████████████████████
Description        service-catalog tutorial token

Be sure to save your token in a safe place! We won't be able to show you it again.
```

Create a cluster service broker using [Manifold][manifold]. Make sure to use
your API token in the command:

```bash
MANIFOLD_API_TOKEN="<put your token from the previous step here>" \
kubectl apply -f - <<EOF
apiVersion: servicecatalog.k8s.io/v1beta1
kind: ClusterServiceBroker
metadata:
  name: manifold-broker
spec:
  url: "https://:$MANIFOLD_API_TOKEN@osb.manifold.co"
EOF
```
<br>

**Next:** [Explore the service-catalog data](explore-the-service-catalog-data.md)

[manifold]: https://www.manifold.co
