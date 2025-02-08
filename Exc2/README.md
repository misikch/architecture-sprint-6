```bash
minikube start
minikube addons enable metrics-server # включаем metrics-server
kubectl get pods -n kube-system | grep metrics-server # убедиться, что сервер метрик запущен.
kubectl apply -f deployment.yaml
kubectl get pods -w # актуальный статус подов

kubectl apply -f service.yaml
kubectl get svc
kubectl apply -f hpa.yaml
minikube service testapp --url

minikube dashboard --url
kubectl describe hpa testapp-hpa
```

