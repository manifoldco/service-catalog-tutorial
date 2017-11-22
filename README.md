# service-catalog Tutorial

The service-catalog tutorial walks you through installing
[service-catalog][svccat], and using it in your [Kubernetes][k8s] cluster to
create and use external cloud services.

This tutorial will demonstrate how to use the service-catalog to find and
configure the ([LogDNA][logdna] log aggregator to ship your cluster's logs to a
central logation for analysis, all from within Kubernetes. You will aggreggate
both the logs of kubernetes itself, and those of a sample application.

In this tutorial, you will use [Manifold][manifold] as the source of your cloud
services. service-catalog uses the [Open Service Broker API][osbapi], so you
can apply  these concepts to many more services, like those in [Google Cloud
Platform][gcposb]

## Prerequisites

- [Prerequisites](./labs/prerequisites.md)

## Tutorial

- [Start Minikube](./labs/start-minikube.md)
- [Run a sample application](./labs/run-a-sample-application.md)
- [Install and configure service-catalog](./labs/install-and-configure-service-catalog.md)
- [Configure the Manifold service broker](./labs/configure-the-manifold-service-broker.md)
- [Explore the service-catalog data](./labs/explore-the-service-catalog-data.md)
- [Find and create a log aggregator](./labs/find-and-create-a-log-aggregator.md)
- [Use the log aggregator](./labs/use-the-log-aggregator.md)

## Cleanup

- [Cleanup](./labs/cleanup.md)

## See Also

- The [service-catalog][svccat] Kubernetes incubator repository.
- The [Open Service Broker API][osbapi] Specification.
- Manifold's [kubernetes-credentials][k8screds] controller, to use existing
  resources in Kubernetes.

## Acknowledgements

The structure of this tutorial was heavily inspired by tutorials from [Kelsey
Hightower][hightower]. Check them out; he's great!

[k8s]: https://kubernetes.io/
[manifold]: https://www.manifold.co/
[logdna]: https://www.manifold.co/services/logdna
[gcposb]: https://github.com/GoogleCloudPlatform/k8s-service-catalog
[svccat]: https://github.com/kubernetes-incubator/service-catalog
[osbapi]: https://github.com/openservicebrokerapi/servicebroker/
[k8screds]: https://github.com/manifoldco/kubernetes-credentials
[hightower]: https://github.com/kelseyhightower
