## IPID Workflow

### Token Vending & AWS Credentials

Before interacting with the EKS cluster, ensure your AWS credentials are up to date and your session token is valid.  
1. Retrieve a new authentication token from the **token vending machine**.  
2. Update your local AWS credentials under `~/.aws/credentials` and `~/.aws/config` with the new values.  
3. Finally, update your kubeconfig to point to the correct EKS cluster:

```shell
aws eks update-kubeconfig --region eu-central-1 --name eks-dev-platform
```

This ensures that `kubectl` commands communicate with the `eks-dev-platform` cluster in the `eu-central-1` region using your refreshed credentials.
