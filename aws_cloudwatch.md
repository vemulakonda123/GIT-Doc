# AWS EC2 Monitoring with Cloudwatch | Monitor Memory Utilization using CloudWatch | AWS CloudWatch Demo
## AWS Systems Manager allows you to safely automate common and repetitive IT operations and management tasks across multiple accounts and AWS Regions.
## Steps:

### Step 1: Create an IAM and Attach CloudWatch and SSM Full Access - EC2-CloudWatch-Role
### Step 2: Create a parameter in Systems Manger with the name "/alarm/AWS-CWAgentLinConfig" and store the value.
### Step 3: Create an EC2 Instance, Attach the role created in Step 1 and Add the commands in the Userdata Section.


## Commands that needs to be added in Userdata Section:
```bash
#!/bin/bash
wget https://s3.amazonaws.com/amazoncloudwatch-agent/linux/amd64/latest/AmazonCloudWatchAgent.zip
unzip AmazonCloudWatchAgent.zip
sudo ./install.sh
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -c ssm:/alarm/AWS-CWAgentLinConfig -s
```
## Check if EC2 Instance has CWAgent Installed or not:
```bash
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -m ec2 -a status
```
```
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -m ec2 -a start
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -m ec2 -a restart
-m ec2: Specifies the mode in which the CloudWatch Agent is running. In this case, it is running on an EC2 instance.
-a status: The -a option specifies the action to perform. status checks the current status of the CloudWatch Agent.
```
## Value for the SSM Parameter (/alarm/AWS-CWAgentLinConfig):  >>>> for memory
```bash
{
	"metrics": {
		"append_dimensions": {
			"InstanceId": "${aws:InstanceId}"
		},
		"metrics_collected": {
			"mem": {
				"measurement": [
					"mem_used_percent"
				],
				"metrics_collection_interval": 60
			}
		}
	}
}
```
## Value for the SSM Parameter (/alarm/AWS-CWAgentLinConfig): >>>>for memory and disk utlization
```
{
	"metrics": {
		"append_dimensions": {
			"InstanceId": "${aws:InstanceId}"
		},
		"metrics_collected": {
			"mem": {
				"measurement": [
					"mem_used_percent"
				],
				"metrics_collection_interval": 60
			},
           		 "disk": {
				"measurement": [
                    			 "disk_used_percent"
				],
				"metrics_collection_interval": 60
			}
		}
	}
}
```
## for multiple instance 
```
{
	"metrics": {
		"append_dimensions": {
			"InstanceId": "${aws:InstanceId}",
			"InstanceType": "${aws:InstanceType}",
			"Region": "${aws:Region}"
		},
		"metrics_collected": {
			"mem": {
				"measurement": [
					"mem_used_percent"
				],
				"metrics_collection_interval": 60
			},
               		 "disk": {
				"measurement": [
                                     "disk_used_percent"
				],
				"metrics_collection_interval": 60
			}
		}
	}
}

```




## Reference/Additional Reading:
1. https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent-New-Instances-CloudFormation.html
2. https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch-Agent-Configuration-File-Details.html
