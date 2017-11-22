# Start Minikube

[Minikube][minikube] runs Kubernetes locally inside a virtual machine. Start it
and verify it is working correctly:

```bash
# start minikube. this assumes you're using mac os.
# enabling RBAC (Role Based Access Control) is required for service-catalog
minikube start --vm-driver=xhyve --extra-config=apiserver.Authorization.Mode=RBAC
```
```bash
kubectl get all
```
```
NAME             TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
svc/kubernetes   ClusterIP   10.0.0.1     <none>        443/TCP   29s
```

<br>

**Next:** [Run a sample application](run-a-sample-application.md)

[minikube]: https://github.com/kubernetes/minikube
