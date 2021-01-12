### install DAPR components

    dapr init -k --enable-mtls=false --runtime-version 1.0.0-rc.2
    dapr status -k

### set up pubsub and statestore

    helm install redis bitnami/redis
