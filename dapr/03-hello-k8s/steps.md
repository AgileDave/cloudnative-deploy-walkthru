### deploy node app

    kubectl apply -f node.yaml -n agileball

    http://52.147.208.36/ports

### deploy python app

    kubectl apply -f python.yaml -n agileball

    kubectl logs --selector=app=node -c node

    http://<EXT_IP>/order
