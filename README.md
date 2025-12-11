# AWS Cloud Native MLPS Solution
This is the AWS Cloud Native MLPS Solution, which we have launched in the AWS China regions website solution library,see [Link](https://www.amazonaws.cn/en/solutions/technology/security/guidance/amazon-cloud-native-mlps-solution/amazon-solution-guide/) for more information.

AWS Cloud Native MLPS Solution is a cloud-native security service and operations management solution for cloud tenants, based on a shared responsibility model. It meets the requirements of both Level 2 and Level 3 MLPS compliance for tenants. This solution not only provides the necessary products and services to meet the technical requirements of different levels of MLPS, but also offers a Runbook document for building the solution on existing workloads in the cloud environment, facilitating rapid construction of a secure cloud environment. This solution not only meets MLPS Compliance requirements but also helps customers improve their security baseline, conforming to AWS WA security best practices. For customers using both global AWS cloud services and Amazon China cloud services, it ensures consistency in security solutions, unifies security operations management, and avoids additional operational burdens.

# Solution Architecture
The solution architecture is shown as below：
![image](https://github.com/liyangln-AWS/aws-mlps-solution-deployment/blob/main/mlps-architecture.png)

# Runbook
This runbook document provides a complete step-by-step guide on how to create a basic cloud environment, configure security capabilities, and verify the effectiveness of security protection within the AWS China regions cloud environment. Each step is explained in detail, including why these security components need to be deployed and how to deploy them, accompanied by screenshots and detailed step-by-step instructions for easy understanding.

# Security services configuration src
For some security products (GuardDuty, Inspector, WAF, Security Hub), we offer an automated deployment method (AWS CloudFormation Code) to help customers deploy the necessary products and features with one click, simplifying the operation process.
