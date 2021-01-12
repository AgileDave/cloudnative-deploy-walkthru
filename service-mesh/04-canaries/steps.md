### Install Flagger

    kubectl apply -k github.com/weaveworks/flagger/kustomize/linkerd

### Set up the demo deploy

    kubectl create ns test && kubectl apply -f flagger-demo.yml

### port-forward

    kubectl port-forward svc/frontend -n test 8080:8080

### Configure the Canary Rollout Strategy

    kubectl apply -f podinfo-canary.yaml

### Update the deployment image to a 'newer' version (start rollout)

    kubectl -n test set image deployment/podinfo podinfod=quay.io/stefanprodan/podinfo:1.7.1

### Watch the Canary resource

    watch kubectl -n test get canary

### Inspect the TrafficSplit resource

    kubectl -n test get trafficsplit podinfo -o yaml

### Reset it back

    kubectl -n test set image deployment/podinfo podinfod=quay.io/stefanprodan/podinfo:1.7.0
