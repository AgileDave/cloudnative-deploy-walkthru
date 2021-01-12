### Deploy hipster app (may have to apply twice if ns isn't created first)

#### Linkerd annotations already in place

    kubectl apply -f hipster/hipster-ns.yaml
    kubectl apply -f hipster/.

### Startup the dashboard again

    linkerd dashboard

### port-forward

    kubectl port-forward svc/frontend -n hipster 8888:80
