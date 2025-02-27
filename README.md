# Kubernetes Cheatsheet

## Kubernetes Architecture
Kubernetes follows a **master-worker** architecture, comprising several key components:

### **Master Node (Control Plane)**
1. **API Server** – Acts as the front-end for Kubernetes.
2. **Controller Manager** – Ensures the desired state of the cluster.
3. **Scheduler** – Assigns workloads (Pods) to worker nodes.
4. **etcd** – A key-value store that maintains cluster state.

### **Worker Node**
1. **Kubelet** – Ensures containers run as expected.
2. **Kube Proxy** – Manages networking between services.
3. **Container Runtime** – Executes containers (e.g., Docker, containerd, CRI-O).

---

## Commonly Used Kubernetes Commands

### **Cluster & Node Management**
```sh
kubectl cluster-info         # Show cluster info
kubectl get nodes            # List nodes
kubectl describe node <node> # Detailed info of a node
kubectl cordon <node>        # Mark a node as unschedulable
kubectl drain <node>         # Safely evict all pods from a node
kubectl uncordon <node>      # Mark a node as schedulable again
```

### **Pod Management**
```sh
kubectl get pods                      # List all pods
kubectl describe pod <pod_name>       # Show pod details
kubectl logs <pod_name>               # View logs of a pod
kubectl exec -it <pod_name> -- /bin/sh  # Access a running pod shell
```

### **Deployment & Service Management**
```sh
kubectl get deployments               # List all deployments
kubectl describe deployment <name>    # Show deployment details
kubectl scale deployment <name> --replicas=3  # Scale a deployment
kubectl delete deployment <name>      # Delete a deployment
kubectl get svc                        # List services
kubectl expose deployment <name> --type=LoadBalancer --port=80  # Expose service
```

### **ConfigMap & Secret Management**
```sh
kubectl create configmap my-config --from-literal=key=value  # Create a ConfigMap
kubectl get configmaps                            # List all ConfigMaps
kubectl describe configmap my-config              # Show details of a ConfigMap
kubectl delete configmap my-config                # Delete a ConfigMap

kubectl create secret generic my-secret --from-literal=password=pass123  # Create a Secret
kubectl get secrets                            # List all Secrets
kubectl describe secret my-secret              # Show details of a Secret
kubectl delete secret my-secret                # Delete a Secret
```

### **Namespace Management**
```sh
kubectl get namespaces           # List all namespaces
kubectl create namespace dev      # Create a namespace
kubectl delete namespace dev      # Delete a namespace
```

### **Persistent Volume (PV) & Persistent Volume Claim (PVC)**
```sh
kubectl get pv                    # List persistent volumes
kubectl get pvc                   # List persistent volume claims
kubectl describe pvc <pvc_name>   # Show details of a PVC
```

### **Helm (Package Management for Kubernetes)**
```sh
helm repo add stable https://charts.helm.sh/stable  # Add Helm repo
helm install my-release stable/nginx                # Install a Helm chart
helm list                                          # List installed charts
helm upgrade my-release stable/nginx               # Upgrade an existing chart
helm uninstall my-release                          # Remove a Helm release
```

### **Monitoring & Debugging**
```sh
kubectl top nodes             # Show resource usage of nodes
kubectl top pods              # Show resource usage of pods
kubectl get events            # Get cluster events
kubectl describe pod <pod>    # Show detailed pod information
kubectl get all -A            # Show all resources across all namespaces
```

---

### **Useful Kubernetes Resources**
- [Kubernetes Official Docs](https://kubernetes.io/docs/)
- [Kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [Helm Charts](https://helm.sh/docs/)

---

🚀 **Stay ahead in the DevOps world by mastering Kubernetes!**

