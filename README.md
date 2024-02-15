# kubernetes-learning

sample deployment files for Kubernetes objects

# Minikube

Minikube installation:

Setup:

1. Installing minikube

   curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

   sudo install minikube-linux-amd64 /usr/local/bin/minikube

2. Verifying Minikube installation

   minikube version

3. Starting Minikube

   minikube start -p minikube-demo --output='text' --nodes 3 --cpus='2' --disk-size='20000mb' --container-runtime='docker' --cni='calico' --cache-images=true --driver='docker' --force-systemd=true --extra-config=kubelet.cgroup-driver=systemd --wait-timeout=6m0s --delete-on-failure=false --kubernetes-version=v1.28.3 --auto-update-drivers=false --force

4. Get pods

   minikube kubectl -- get pods -A

5. Minikube status

   minikube status

6. Minikube profile list

   minikube profile list

7. Current profile

   minikube profile

8. Switch profile

   minikube profile minikube-demo

9. Minikube status

   minikube status

10. Rename worker nodes

    minikube kubectl label node minikube-demo-m02 node-role.kubernetes.io/worker=worker

    minikube kubectl label node minikube-demo-m03 node-role.kubernetes.io/worker=worker

11. Add worker node role

    minikube kubectl label nodes minikube-demo-m02 role=worker

    minikube kubectl label nodes minikube-demo-m03 role=worker

12. Apply minikube deployment

    minikube kubectl -- apply --filename redis-deployment.yaml

13. Get pod details

    minikube kubectl -- get pods -o wide

14. Get pod logs

    minikube kubectl -- logs redis-deploy-75d5csssd9-gwbfx

15. describe pod

   minikube kubectl -- describe pods <podname>
