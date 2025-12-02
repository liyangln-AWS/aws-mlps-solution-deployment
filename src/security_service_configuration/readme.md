
#enable-guardduty-features-for-mlps.yaml:
This template will deploy the GuardDuty service with the Foundational protection plans (VPC Flow Logs, DNS logs, and CloudTrail Management Events) enabled by default, plus the explicitly configured Malware Protection for EC2 instances.There are many extended features in GuardDuty, including S3 Protection, Kubernetes Protection, and Malware Protection for EC2. S3 Protection and Kubernetes Protection is not required by MLPS so these features are not enabled in this yaml. If you need these features for security or other complicance requirement, you can enable they later.

#enable-inspector-features-for-mlps.yaml:
We use Amazon Inspector V2 for CVEs scan for EC2 instance. Currently, AWS CloudFormation does not have a native resource type to simply enable Amazon Inspector V2 and its scanning features (EC2, ECR, Lambda). To achieve automatic deployment with specific features like EC2 only, the best practice is to use a CloudFormation Custom Resource backed by an AWS Lambda function that calls the Inspector API.
This template performs three main actions:
1.Creates an IAM Role for the Lambda function.
2.Creates a Python Lambda function to call the Inspector Enable API.
3.Defines a Custom Resource to execute the Lambda, enabling Inspector V2 for EC2 scanning only.
Important Notes: For Amazon Inspector to perform deep vulnerability scanning on your EC2 instances, the instances must be AWS Systems Manager (SSM) managed instances with the SSM Agent installed and running, and they need an appropriate IAM instance profile (AmazonSSMManagedInstanceCore).

#create-waf-webacl-and-rules-for-mlps.yaml:
This CloudFormation template will automatically deploy an AWS WAFv2 Web ACL named WEBACL_MLPS with a default action of ALLOW. It includes the four requested AWS Managed Rule Groups which are reqired by MLPS, including Core Rule Set (CRS), Admin Protection, Anonymous IP List and Amazon IP Reputation List.
After deploying this template, the Web ACL will exist but won't protect anything yet. You need to associate this Web ACL with an AWS resource such as an Application Load Balancer or API Gateway, CloudFront Distribution is not available yet in AWS China Regions.


#enable-securityhub-features-for-mlps.yaml:
This comprehensive CloudFormation template will automatically enable AWS Security Hub in the current region, activate the AWS Foundational Security Best Practices Standard, configure the required AWS Config resources to support the checks, and ensure GuardDuty and Inspector findings are ingested.The ingested findings and security hub findings are the security center function needed by MLPS.
Improtant note:When deploying this CloudFormation stack, you will need to provide a globally unique name for the S3 bucket used by AWS Config via the S3BucketName parameter.
