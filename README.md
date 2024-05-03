Testing Commands:

    helm install clickhouse-release clickhouse1/ --values clickhouse1/values.yaml
    helm upgrade clickhouse-release clickhouse1/ --values clickhouse1/values.yaml
    helm upgrade myhelmapp-release clickhouse1/ --values clickhouse1/values.yaml

Post-Deployment Verification:

    helm ls: To list installed Helm releases.
    kubectl get all: To view Kubernetes resources.
    servicename=$(k get service -l "app=myhelmapp" -o jsonpath="{.items[0].metadata.name}"): Command to fetch the service name.
    kubectl port-forward service/myhelmapp 8888:80 --namespace default: Command for port forwarding.
