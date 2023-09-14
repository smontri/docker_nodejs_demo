# GitHub Action Worflow to Build, Scan by Prisma Cloud and Push To ECR Registry a Container Image

Build, Scan and Deploy a simple NodeJS image to an AWS ECR Registry with GitHub Action and Prisma Cloud

1. AWS ECR Repository is created during GitHub Action process (control if repository exists and create if not)
2. Prisma Cloud checks vulnerabilities and compliance during build phase before pushing image to AWS ECR Registry
3. Depending on Prisma Cloud configuration, the build may be rejected and deployment prohibited (Hard Fail). 
4. Errors can be injected into the Dockerfile to force failure (for demonstration purposes) 

If you want to use the Prisma Cloud security control on your Dockerfile in your Github repo, you can.
Usage: deploy this workflow in the GitHub repository containing your Dockerfile, update the variables and secret in your GitHub repository settings (Prisma Access/Secret Key, AWS Secret, etc.).

### Author: Christopher LEY - cley@paloaltonetwork.com
