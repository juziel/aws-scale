# aws-scale
A quick script for changing autoscaling group instance numbers for promotions and events.

# Requirements
- aws-cli

# Usage
```shell
aws-scale [--stack stackname(required)] [--min num_asg_minimum(required)] [--max num_asg_maximum(required)] [--des num_asg_desired(required)] [--profile aws_profile] [--region aws_region]
```

If the exact autoscaling group is not entered for stackname, the input is used to produce a list via fuzzy matching. The script will then submit the change to the autoscaling group.

```
$ aws-scale --stack example --min 10 --max 30 --des 20
1) example-AutoScalingGroup-ZGL5HRS9D364
#? 1
Modifying example-AutoScalingGroup-ZGL5HRS9D364:
Modifying minimum from 2 to 10
Modifying maximum from 4 to 30
Modifying desired from 2 to 20

$ aws-scale --stack example-AutoScalingGroup-ZGL5HRS9D364 --min 2 --max 2 --des 2
Modifying example-AutoScalingGroup-ZGL5HRS9D364:
Modifying minimum from 10 to 2
Modifying maximum from 30 to 4
Modifying desired from 20 to 2
```
