# eks-cfn

Setup an [AWS EKS](https://docs.aws.amazon.com/eks/latest/userguide/getting-started.html) Cluster via CloudFormation using
[AWS-managed NodeGroups](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-eks-nodegroup.html).

## Setup

Create the cluster
```bash
VPC_ID=vpc-1234567890123
SUBNET_IDS=subnet-1,subnet-2,subnet-3
CLUSTER_NAME=my-prod-cluster

aws cloudformation deploy \
  --template-file ./eks.yaml \
  --stack-name $CLUSTER_NAME \
  --parameter-overrides VpcId=$VPC_ID \
    SubnetIds=$SUBNET_IDS \
    ClusterName=$CLUSTER_NAME \
  --capabilities CAPABILITY_IAM
```
