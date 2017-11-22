# Cleanup

## Deprovision your LogDNA resource in Manifold

Deprovision your resource:

```bash
manifold delete $YOUR_RESOURCE_NAME_HERE
```

```
✔ Resource: tasteful-vanilla-dodecahedron (Tasteful Vanilla Dodecahedron)
✔ Are you sure you want to delete "tasteful-vanilla-dodecahedron": y
Your instance "tasteful-vanilla-dodecahedron" has been deleted
```

## Remove the Manifold API token

Find the token you created:

```bash
manifold tokens list
```
```
1 tokens found
Use `manifold tokens delete [token-id]` to revoke a token

ID                                   Token               Description                           Role
21m922akywq6qwk2x01pr3a0vpk6r        Gt5R****WXTl        service-catalog tutorial token        write
```

Delete the token. Make sure to use your token ID:

```bash
manifold tokens delete $ID_FROM_ABOVE
```

## Shut down Minikube

Delete the virtual machine used to run Kubernetes. This will stop the running
instance, too:

```sh
minikube delete
```
<br>

**Next**: [Return to the overview](../README.md)
