### Check cluster

    linkerd check --pre

### Install Linkerd

    linkerd install | kubectl apply -f -

### Check status

    linkerd check

### Update linkerd with tracing for later use

    linkerd upgrade --config config.yaml | kubectl apply -f -

### Check status to make sure tracing is enabled

    linkerd check

### Install EmojiVoto into cluster

    curl -sL https://run.linkerd.io/emojivoto.yml | kubectl apply -f -

### Inject linkerd into emojivoto

    kubectl get -n emojivoto deploy -o yaml | linkerd inject -  | kubectl apply -f -

### Verify all is running well

    linkerd -n emojivoto check --proxy

### Port-forward

    kubectl port-forward svc/web-svc -n emojivoto 8888:80

### Uninstall Linkerd

    linkerd uninstall | kubectl delete -f -
