# Installation for clickouse and superset

## Requirements
### Setup
- Create superset installation
- Create a clickhouse statefulset.
    - Persistant volume of 10Gb
    - servic exposed on port 9000
### Functional
- Add clickhouse as a data source in superset inside the K8s cluster

## Steps to follow

### Clickhouse installation

| install the clickhouse[./clickhouse-operator.yaml]
```shell
kubectl apply -f clickhouse-operator.yaml -n default
```
| insttall the clickhouse-cluster[./clickhouse-cluster.yaml] using the operator
```shell
kubectl apply -f clickhouse-cluster.yaml -n default
```
| install the superset cluster[./superset.yaml]
```shell
kubectl apply -f superset.yaml
```

## Final Result
![Kubernetes resource image](kubernetes-resources.png)
![Superset image](final-screenshot.png)