# kubernetes-getting-started

__Build container image with docker__

- docker image build -t  <dockerhub-registry>/<name-of-repo>:1.0 .
- docker image push <dockerhub-registry>/<name-of-repo>:1.0

__Single and multi-container pods__

- kubectl apply -f <name-of-pod-file>
- kubectl get pods -o wide
- kubectl describe pods <name-of-pod>
- kubectl delete pod <name-of-pod>  || kubectl delete -f <name-of-pod-file>
