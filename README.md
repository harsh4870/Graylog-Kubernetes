# Graylog-Kubernetes
Graylog kubernetes cluster with mongodb elastic search using helm chart


## Dependencies
This chart is dependent on:
Mongo-db replica : https://github.com/helm/charts/tree/master/stable/mongodb-replicaset

## Installing the Chart

To install the chart with the release name logs:
```
$ helm install --name logs .  --set graylog.passwordSecret=<16+ CHARS PASSWORD> --set ingress.domain=test.com --namespace=monitoring
```
The application will be accessible via http://logs.test.com

To install the chart when working with reverse proxy

```text
$ helm install --name logs .  --set graylog.passwordSecret=<16+ CHARS PASSWORD> --set ingress.domain=test.com --namespace=monitoring --set ingress.proxyDomain=<EXTERNAL DOMAIN>
```
## Configuration

All service will running with peristense volume claim so PV support on the underlying infrastructure must.

Mongo DB : statefulset
Elastic Search : statefulset
Gryalog : statefulset
   
