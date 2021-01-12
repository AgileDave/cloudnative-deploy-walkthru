### enable tracing in the cluster

    dapr configurations --kubernetes

    kubectl apply -f appconfig.yaml

    dapr configurations --kubernetes

### deploy zipkin

    kubectl apply -f zipkin.yaml
