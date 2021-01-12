### create agileball namespace

    kubectl apply -f agileball-ns.yaml

### create pubsub store and statestore

    kubectl apply -f dapr-pubsub.yaml
    kubectl apply -f dapr-statestore.yaml
