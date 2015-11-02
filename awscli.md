
# AWS CLI

## Output neat looking table of EC2 instances

```
aws ec2 describe-instances --query 'Reservations[].Instances[].[ [Tags[?Key==`Name`].Value][0][0],PrivateIpAddress,InstanceId,State.Name,InstanceType,Placement.AvailabilityZone,VpcId ]' --output table
```