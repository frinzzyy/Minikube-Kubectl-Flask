# Exercise 2 — Flask on Minikube

```bash
minikube start
docker build -t flask-app:1.0 .
minikube image load flask-app:1.0
kubectl apply -f k8s.yaml
kubectl rollout status deployment/flask-app
kubectl get deploy,pods,svc
minikube service flask-app
```

Expected HTTP body: `Hello from Flask on Kubernetes!`. If using a Docker driver and a separate Docker daemon, `minikube image load` makes the image available to the cluster. Cleanup: `kubectl delete -f k8s.yaml`.
