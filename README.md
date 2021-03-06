# kubernetes-getting-started

__Build container image with docker__

- docker image build -t  dockerhub-registry/name-of-repo:1.0 .
- docker image push dockerhub-registry/name-of-repo:1.0

__Single and multi-container pods__

- kubectl apply -f name-of-pod-file
- kubectl get pods -o wide
- kubectl describe pods name-of-pod
- kubectl delete pod name-of-pod  || kubectl delete -f name-of-pod-file

__kubernetes services (Configuring NodePorts: The imperative way)__

- kubectl expose pod name-of-pod --name=name-to-be-registered-with-DNS --target-port=8080 --type=NodePort
- kubectl get svc
- (on a web browser, visit IP-of-cluster-node:NodePort)
- kubectl delete svc name-of-service

__kubernetes services (Configuring NodePorts: The declarative way)__

- kubectl get pods --show-labels
- (Within the services folder) kubectl apply -f svc-nodeport.yml 
- kubectl describe svc name-of-service

__Kubernetes services (Load balancers)__

- kubectl apply -f svc svc-lb.yml
- kubectl get svc
- (on a web browser, visit load balancer public IP Address)

__Kubernetes deployments__

- (Within the deployments folder) kubectl apply -f deploy.yml
- kubectl get pods
- kubectl get deploy
- kubectl get rs(replica set)
- kubectl apply -f ../Services/svc-lb.yml
- kubectl describe avs ps-lb
- kubectl get pods --show-labels
- kubectl get ep(endpoints) || kubectl describe ep ps-lb
- kubectl get svc
- // Self-healing
- kubectl delete pod some-pod
- kubectl get pods 
- kubectl get pods -o wide (shows nodes on which pods are running on)
- (after deleting one node) kubectl get nodes 
- //Autoscaling
- change the replica field value in deployment.yml file
- run deployment
- (Horizontal pod autoscaler and cluster autoscaler)
- // Rolling updates
- kubectl get pods --watch
- kubectl rollout status deploy name-of-deployment
- kubectl get rs
- kubectl describe rs name-of-hashed-deployment
- kubectl rollout history deploy name-of-deployment
- // Rollbacks
- kubectl rollout undo deploy name-of-deployment --to-revision=revisionNumber
- kubectl get rs

