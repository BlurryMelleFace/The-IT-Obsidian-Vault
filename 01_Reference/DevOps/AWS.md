##  Authentication

```shell
aws configure                # Set access key, secret key, region, output format
aws configure list           # Show active credentials/config
aws sts get-caller-identity  # Verify current identity
aws sso login --profile <p>  # Login with AWS SSO
```

---

## General

```shell
aws ec2 describe-regions --output table
aws ec2 describe-availability-zones --region <region>
```

---

##  EKS (Kubernetes)

```shell
aws eks list-clusters --region <region>
aws eks describe-cluster --name <cluster> --region <region>
aws eks update-kubeconfig --name <cluster> --region <region> --profile <p>
```

---

##  S3

```shell
aws s3 ls
aws s3 ls s3://<bucket>
aws s3 cp file.txt s3://<bucket>/file.txt
aws s3 sync ./localdir s3://<bucket>/ --delete
```

---

## EC2

```shell
aws ec2 describe-instances --region <region>
aws ec2 start-instances --instance-ids <id>
aws ec2 stop-instances --instance-ids <id>
aws ec2 reboot-instances --instance-ids <id>
```

---

##  IAM

```shell
aws iam list-users
aws iam list-roles
aws iam list-policies
```

---

## ECR (Elastic Container Registry)

```shell
aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <account>.dkr.ecr.<region>.amazonaws.com
aws ecr describe-repositories
aws ecr list-images --repository-name <repo>
```

---

## CloudWatch

```shell
aws logs describe-log-groups
aws logs describe-log-streams --log-group-name <group>
aws logs get-log-events --log-group-name <group> --log-stream-name <stream>
```

1. Token vedning machine
2. Update credentials in .aws 
3. aws eks update-kubeconfig --region eu-central-1 --name eks-dev-platform

