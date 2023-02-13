# Agent/Gateway OpenTelemetry Operator for Kubernetes Demo

### Install k8s operator
```
kubectl create namespace opentelemetry-operator
helm upgrade --install --namespace opentelemetry-operator opentelemetry-operator open-telemetry/opentelemetry-operator
```

### Create namespace and apply Gateway CR
```
kubectl create namespace ns-gateway
kubectl --namespace ns-gateway apply -f agent-gateway/gateway.yaml
```

### Create namespace and apply Agent CR
```
kubectl create namespace ns-app
kubectl --namespace ns-app apply -f agent-gateway/agent.yaml
```

### Apply demo app
```
kubectl --namespace ns-app apply -f agent-gateway/app.yaml
```
