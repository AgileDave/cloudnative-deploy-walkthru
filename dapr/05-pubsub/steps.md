### deploy node subscriber

    kubectl apply -f node-subscriber.yaml -n agileball

### deploy pytyon subscriber

    kubectl apply -f python-subscriber.yaml -n agileball

### deploy react form

    kubectl apply -f react-form.yaml -n agileball

### run form

    http://<EXT_IP>

### port forward on zipkin

    kubectl port-forward svc/zipkin 9411:9411
