# Build, scan and deploy a docker image to an AWS ECR registry securely with Prisma Cloud and GitHub Action.



#### Objectifs

Github Action pipeline to build and deploy a docker image in an AWS ECR.

Build, Scan and Deploy a simple NodeJS image to an AWS ECR Registry with GitHub Action and Prisma Cloud

The image is tested and validated by Prisma Cloud, to check for vulnerabilities and compliance and authorize or not the deployment to the AWS ECR Registry.

#### Requirements

- **GitHub Account** to create private fork
- **AWS Subscription** with Programmatic Access (**AWS_ACCESS_KEY_ID / AWS_SECRET_ACCESS_KEY** )
- **Prisma Cloud Tenant** with AccessKey & Secret

#### Prerequisites

##### 1. Create a fork of the repository

- Login with your github account
- Open https://github.com/cleypanw/docker_nodejs_demo and click on Fork



##### 2. Configure GitHub Action Secrets

Open **Settings > Security > Secrets and variables > Actions**

- Secrets

  - **AWS_ACCESS_KEY_ID**

  - **AWS_SECRET_ACCESS_KEY**

  - **PCC_CONSOLE_URL** (Prisma Cloud Console URL)

  - **PCC_PASS** (Prisma Cloud Access Key)

  - **PCC_USER** (Prisma Cloud Secret Key)

    



#### Sequence Diagram

![sequence_diagram.png](images/sequence_diagram.png)



#### High Level Diagram 

![HLD](images/hld.png)



#### Rollout

<u>/!\ UNDER CONSTRUCTION /!\</u>

Build, Scan and Deploy a simple NodeJS image to an AWS ECR Registry with GitHub Action and Prisma Cloud.



1. **From GitHub** - Update GitHub Action Secrets

   Go to **Settings => Secrets and Variables**

![Secrets](images/variables_secrets.png)





2. **From IDE** - Create Security Issue : example Edit Dockerfile to add SCA issues by using an [old node base image](https://hub.docker.com/_/node/tags) (here node:14)

![ide](images/ide.png)

***Note that High alerts are reported directly to the IDE***

3. **From Prisma Cloud Console** -  Add New Vulnerabilities Images CI rule to alert / block  image that are built during CI

   Go to **Compute => Defend => Vulnerabilities => Images => CI**

   Set a Rule Name, Alert and Failure Threshold as following and Save

   ![CI-rule](images/CI-rule.png)

1. Depending on Prisma Cloud configuration, the build may be rejected and deployment prohibited (Hard Fail). 
2. Errors can be injected into the Dockerfile to force failure (for demonstration purposes) 





If you want to use the Prisma Cloud security control on your Dockerfile in your Github repo, you can.
Usage: deploy this workflow in the GitHub repository containing your Dockerfile, update the variables and secret in your GitHub repository settings (Prisma Access/Secret Key, AWS Secret, etc.).

### Author: Christopher LEY - cley@paloaltonetwork.com
