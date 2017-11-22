# Explore the service-catalog data

View the available services:

```bash
kubectl get clusterserviceclass \
-o custom-columns=Name:{.spec.externalName},\
ID:{.metadata.name},\
Description:{.spec.description}
```

```
Name                   ID                              Description
websolr                234kw73u6y3vdgdpxqhxbr39vxdmj   Solr, fully managed by the experts in hosted search at One More Cloud.
mailgun                234mauvfd213a0a87q42eb0mmq5ye   The Email Service For Developers
scoutapp               234mh3t2j3gk00veubpxbxmzkzgtp   Track down memory leaks, N+1s, slow code and more. For Ruby & Elixir apps.
logdna                 234qkjvrptpy3thna4qttwt7m2nf6   The best logging service you will ever use
bonsai-elasticsearch   234rrwjuvq3t66r1r0p797p9jvrn2   Elasticsearch, fully managed by the experts in hosted search.
cloudamqp              234u3fyxq4pa2kzcu23w77cd9tq4g   Perfectly configured and optimized RabbitMQ clusters ready in 2 minutes.
redisgreen             234ucbn3xxq2vvemum4e36t3fhqb4   Scalable, Production-Ready Redis
jawsdb-postgres        234udujapvu1yg2fq019qt02ynf1m   Fast, reliable, no-bullshark Postgres as a Service
jawsdb-mysql           234w1jyaum5j0aqe3g3bmbqjgf20p   Fast, reliable, no-bullshark MySQL as a Service
jawsdb-maria           234wx0gvvxnqxyukyn6r7xgy9qm6u   Fast, reliable, no-bullshark MariaDB as a Service
memcachier-cache       234yu3bya4z0t6zwrpvgbfbxrwabp   Reliable and powerful memcache-as-a-service.
```

View the available plans, sorted by service:

```bash
kubectl get clusterserviceplans \
-o custom-columns=Name:{.spec.externalName},\
Service\ ID:{.spec.clusterServiceClassRef.name} \
--sort-by=spec.clusterServiceClassRef.name
```

```
Name              Service ID
standard-large    234kw73u6y3vdgdpxqhxbr39vxdmj
business-small    234kw73u6y3vdgdpxqhxbr39vxdmj
business-large    234kw73u6y3vdgdpxqhxbr39vxdmj
business-medium   234kw73u6y3vdgdpxqhxbr39vxdmj
sandbox           234kw73u6y3vdgdpxqhxbr39vxdmj
standard-small    234kw73u6y3vdgdpxqhxbr39vxdmj
standard-medium   234kw73u6y3vdgdpxqhxbr39vxdmj
pistol            234mauvfd213a0a87q42eb0mmq5ye
musket            234mauvfd213a0a87q42eb0mmq5ye
rifle             234mauvfd213a0a87q42eb0mmq5ye
shotgun           234mauvfd213a0a87q42eb0mmq5ye
```

> *Output omitted for brevity*

<br>

**Next:** [Find and create a log aggregator](find-and-create-a-log-aggregator.md)
