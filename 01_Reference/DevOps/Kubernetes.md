---
tags:
  - devops
  - kubernetes
  - k8s
  - containers
  - cheatsheet
---

# Kubernetes (K8s)

> [!INFO]
> **Kubernetes** is an open-source container orchestration system for automating software deployment, scaling, and management. It is often used to manage clusters of containers built with [[Docker]].

**Related Notes:**
- [[Docker]] – Container runtime and image building.
- [[AWS]] – Cloud provider resources (often used with EKS).


---

## 🔍 Get Resources
1. **Get pod names** (default namespace):
   ```shell
   kubectl get pods -n default
   ```

2. **Get Deployments**:
   ```shell
   kubectl get deployments -n default
   ```

3. **Get Persistent Volume Claims (PVC)**:
   ```shell
   kubectl get pvc -n <ns>
   ```

4. **Get all Services**:
   ```shell
   kubectl get services -n <ns>
   ```

5. **Get Nodes**:
   ```shell
   kubectl get nodes -n <ns>
   ```

6. **Describe Resource** (Detailed view):
   ```shell
   kubectl describe <resourceType> <resourceName>
   ```

7. **Get Namespaces**:
   ```shell
   kubectl get ns
   ```

8. **Get Secrets**:
   ```shell
   kubectl get secret -n <ns>
   ```

9. **Get & Decode Secret** (e.g., postgres password):
   ```shell
   kubectl get secret -n <ns> postgresql -o jsonpath='{.data.postgres-password}' | base64 --decode && echo
   ```

## ⚡ Execute & Interact
1. **Shell into a Pod**:
   ```shell
   kubectl exec -it -n ipid <pod-name> -- /bin/bash
   ```

2. **Run Single Command**:
   ```shell
   kubectl exec <pod-name> -- <command> -n default
   ```

3. **Debug a specific container** (multi-container pod):
   ```shell
   kubectl exec -it <pod-name> --container <container-name> -- /bin/bash
   ```

## 🐞 Debugging
1. **Describe Pod** (Check events/errors):
   ```shell
   kubectl describe pod <pod-name>
   ```

2. **View Logs**:
   ```shell
   kubectl logs <pod-name> -n default
   ```

3. **Follow Live Logs** (`-f`):
   ```shell
   kubectl logs -f <pod-name>
   ```

## 💾 Storage
1. **Get Storage Classes**:
   ```shell
   kubectl get storageclass
   ```

2. **Get Persistent Volumes (PV)**:
   ```shell
   kubectl get pv
   ```

## 🛠 Create & Modify
1. **Apply from YAML** (Create or Update):
   ```shell
   kubectl apply -f <file.yaml>
   ```

2. **Create Namespace**:
   ```shell
   kubectl create namespace <namespace-name>
   ```

3. **Expose Deployment** (Create Service):
   ```shell
   kubectl expose deployment <deployment-name> --type=<service-type> --port=<port>
   ```

4. **Scale Deployment**:
   ```shell
   kubectl scale deployment <deployment-name> --replicas=<number>
   ```

## 🗑 Delete
1. **Delete Pod**:
   ```shell
   kubectl delete pod <pod-name> -n default
   ```

2. **Delete Resource from YAML**:
   ```shell
   kubectl delete -f <file.yaml>
   ```

3. **Delete All Pods in Namespace** (Force Restart):
   ```shell
   kubectl delete pods --all -n ipid
   ```

## ℹ️ Misc & Context
1. **Cluster Info**:
   ```shell
   kubectl cluster-info
   ```

2. **Resource Usage (Metrics)**:
   ```shell
   kubectl top nodes
   kubectl top pods
   ```

3. **Switch Context**:
   ```shell
   kubectl config use-context <context-name>
   ```

4. **Show Current Context**:
   ```shell
   kubectl config current-context
   ```
