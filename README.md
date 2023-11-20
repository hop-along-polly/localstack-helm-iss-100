# localstack-helm-iss-100
A standalone example of the Helm issue reported in https://github.com/localstack/helm-charts/issues/100

## Prerequisites
 - helm
 - minikube
 - kubectl

## Steps to Reproduce

1. Install the App w/ Helm
```bash
helm install my-app .
```
2. List all pods
```bash
kubectl get po
```
3. Forward Port 4566
```bash
kubectl port-forward <pod-id> 4566:4566
```
4. Check if s3://sample-bucket has been created (spoiler alert it's not :sad-panda:)
```bash
aws --endpoint-url=http://localhost:4566 s3 ls 
```
