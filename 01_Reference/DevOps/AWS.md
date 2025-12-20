---
tags:
  - devops
  - aws
  - cloud
  - cheatsheet
  - cli
---
# AWS (Amazon Web Services)

> [!INFO]
> **AWS** offers reliable, scalable, and inexpensive cloud computing services. This note focuses on the `aws` CLI for managing cloud resources like EC2, S3, and EKS.

**Related Notes:**
- [[Kubernetes]] – For EKS (Elastic Kubernetes Service).
- [[Docker]] – For ECR (Elastic Container Registry).


---

## 🔐 Authentication
1. **Configure CLI** (Access Key, Secret, Region):
   ```shell
   aws configure
   ```
2. **List Active Config**:
   ```shell
   aws configure list
   ```
3. **Verify Identity**:
   ```shell
   aws sts get-caller-identity
   ```
4. **SSO Login**:
   ```shell
   aws sso login --profile <profile-name>
   ```

## 📦 S3 (Storage)
1. **List Buckets**:
   ```shell
   aws s3 ls
   ```
2. **List Bucket Content**:
   ```shell
   aws s3 ls s3://<bucket-name>
   ```
3. **Upload File**:
   ```shell
   aws s3 cp file.txt s3://<bucket-name>/file.txt
   ```
4. **Sync Directory** (Local to Remote, deleting missing files):
   ```shell
   aws s3 sync ./localdir s3://<bucket-name>/ --delete
   ```

## 💻 EC2 (Compute)
1. **Describe Regions**:
   ```shell
   aws ec2 describe-regions --output table
   ```
2. **Describe Instances**:
   ```shell
   aws ec2 describe-instances --region <region>
   ```
3. **Start Instance**:
   ```shell
   aws ec2 start-instances --instance-ids <instance-id>
   ```
4. **Stop Instance**:
   ```shell
   aws ec2 stop-instances --instance-ids <instance-id>
   ```
5. **Reboot Instance**:
   ```shell
   aws ec2 reboot-instances --instance-ids <instance-id>
   ```

## ☸️ EKS (Kubernetes)
> *See also: [[Kubernetes]]*

1. **List Clusters**:
   ```shell
   aws eks list-clusters --region <region>
   ```
2. **Describe Cluster**:
   ```shell
   aws eks describe-cluster --name <cluster-name> --region <region>
   ```
3. **Update Kubeconfig** (Connect kubectl to EKS):
   ```shell
   aws eks update-kubeconfig --name <cluster-name> --region <region> --profile <profile>
   ```
   *Example:*
   ```shell
   aws eks update-kubeconfig --region eu-central-1 --name eks-dev-platform
   ```

## 🐳 ECR (Container Registry)
> *See also: [[Docker]]*

1. **Login through Docker**:
   ```shell
   aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <account-id>.dkr.ecr.<region>.amazonaws.com
   ```
2. **List Repositories**:
   ```shell
   aws ecr describe-repositories
   ```
3. **List Images in Repo**:
   ```shell
   aws ecr list-images --repository-name <repo-name>
   ```

## 🛡️ IAM (Identity & Access)
1. **List Users**:
   ```shell
   aws iam list-users
   ```
2. **List Roles**:
   ```shell
   aws iam list-roles
   ```
3. **List Policies**:
   ```shell
   aws iam list-policies
   ```

## 📊 CloudWatch (Logs)
1. **List Log Groups**:
   ```shell
   aws logs describe-log-groups
   ```
2. **List Log Streams**:
   ```shell
   aws logs describe-log-streams --log-group-name <group-name>
   ```
3. **Get Log Events**:
   ```shell
   aws logs get-log-events --log-group-name <group-name> --log-stream-name <stream-name>
   ```

## 📝 Troubleshooting & Notes
- **Token Vending Machine**: Ensure your credentials in `.aws/credentials` are up to date if using temporary tokens.
