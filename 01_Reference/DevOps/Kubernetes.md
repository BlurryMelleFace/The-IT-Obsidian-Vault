## Get
1. Get pod names in the default namespace:
   ```shell
   kubectl get pods -n default
   ```

2. Get Deployments
   ```shell
   kubectl get deployments -n default
   ```

3. Get persistent volume claim status:
   ```shell
   kubectl get pvc -n <ns>
   ```

4. Get all services:
   ```shell
   kubectl get services -n <ns>
   ```

5. Get deployments in a namespace:
   ```shell
   kubectl get deployments -n <ns>
   ```

6. Get nodes in the cluster:
   ```shell
   kubectl get nodes -n <ns>
   ```

7. Get details of a specific resource:
   ```shell
   kubectl describe <resourceType> <resourceName>
   ```

8. Get all namespaces in a cluster
   ```shell
   kubectl get ns
   ```
   
9. Get Secrets
   ```shell
   kubectl get secret -n <ns>
   ```

10. Get Secrets and decode (example database)
   ```shell
kubectl get secret -n <ns> postgresql -o jsonpath='{.data.postgres-password}' | base64 --decode && echo
```
## Execute
1. Look inside a Kubernetes pod (open a shell):
   ```shell
   kubectl exec -it -n ipid <pod-name> -- /bin/bash
   ```

2. Run a single command in a pod:
   ```shell
   kubectl exec <pod-name> -- <command> -n default
   ```
## Debug
1. Describe a problem in a pod:
   ```shell
   kubectl describe pod <pod-name>
   ```

2. View logs of a specific pod:
   ```shell
   kubectl logs <pod-name> -n default
   ```

3. Follow live logs of a pod:
   ```shell
   kubectl logs -f <pod-name>
   ```

4. Debug a container in a pod:
   ```shell
   kubectl exec -it <pod-name> --container <container-name> -- /bin/bash
   ```

## Storage

1. Get storage classes in the cluster:
   ```shell
   kubectl get storageclass
   ```

2. Get persistent volumes in the cluster:
   ```shell
   kubectl get pv
   ```

## Create
1. Create a resource from a YAML file:
   ```shell
   kubectl apply -f <file.yaml>
   ```

2. Create a namespace:
   ```shell
   kubectl create namespace <namespace-name>
   ```

3. Expose a deployment as a service:
   ```shell
   kubectl expose deployment <deployment-name> --type=<service-type> --port=<port>
   ```
   ## Delete
1. Delete a pod:
   ```shell
   kubectl delete pod <pod-name> -n default
   ```

2. Delete a namespace:
   ```shell
   kubectl delete namespace <namespace-name>
   ```

3. Delete a resource using a YAML file:
   ```shell
   kubectl delete -f <file.yaml>
   ```

4. Delete the entire deployment
   ```shell
   kubectl delete deployment -n default
   ```
   
5. Delete all pods
   ```shell
   kubectl delete pods --all -n ipid
   ```
## Miscellaneous
1. Scale a deployment:
   ```shell
   kubectl scale deployment <deployment-name> --replicas=<number>
   ```

2. Apply changes to a resource:
   ```shell
   kubectl apply -f <file.yaml>
   ```

3. View cluster information:
   ```shell
   kubectl cluster-info
   ```

4. Check resource usage:
   ```shell
   kubectl top nodes
   kubectl top pods
   ```

5. Set a context for kubectl commands:
   ```shell
   kubectl config use-context <context-name>
   ```

6. View current context:
   ```shell
   kubectl config current-context
   ```

## IPID

1. See the Pods:
   ```shell
   kubectl get pods -n ipid
   ```
2. Restart all the Pods:
   ```shell
   kubectl delete pods --all -n ipid
   ```
