# 🚀 DevOps Accelerator – Serverless Cloud Project

This project is an end-to-end DevOps implementation built on AWS.  
It shows how to automate infrastructure, deployments, file uploads, and monitoring using modern DevOps practices.

The entire system is serverless and fully automated using Terraform and GitHub Actions.

---

## 📌 What This Project Does

- Hosts a static frontend using S3 and CloudFront
- Allows users to upload files securely
- Uses pre-signed URLs for safe file uploads
- Automatically processes uploaded files using AWS Lambda
- Stores logs in CloudWatch
- Sends email notifications using SNS
- Deploys everything using Terraform + CI/CD

---

## 🏗 How the System Works (Step by Step)

1. User opens the website (hosted on S3 + CloudFront).
2. User uploads a file (JPG, PNG, or PDF).
3. Backend Lambda generates a pre-signed URL.
4. File is uploaded securely to S3.
5. S3 triggers another Lambda function.
6. The file is processed.
7. Logs are saved in CloudWatch.
8. Email notification is sent using SNS.

This setup is fully automated and event-driven.

---

## 🛠 Technologies Used

- AWS S3 (Storage + Website Hosting)
- AWS CloudFront (CDN)
- AWS Lambda (Backend processing in Python)
- API Gateway
- SNS (Email notifications)
- CloudWatch (Monitoring and logs)
- IAM (Security and permissions)
- Terraform (Infrastructure as Code)
- GitHub Actions (CI/CD automation)

---

## ☁ Infrastructure as Code

Infrastructure is created using Terraform.

- Remote state is stored in S3
- DynamoDB is used for state locking
- No manual `terraform apply`
- Infrastructure changes go through GitHub Actions

This makes the setup safe and reproducible.

---

## 🔁 CI/CD Automation

Whenever code is pushed to the `main` branch:

- Terraform validates infrastructure
- Lambda functions are packaged and deployed
- Frontend files are uploaded to S3
- CloudFront updates automatically

All AWS credentials are stored securely using GitHub Secrets.

---

## 🔐 Secure File Upload Method

Instead of making S3 public:

- Lambda creates a temporary pre-signed upload URL
- User uploads file using that URL
- S3 triggers backend processing automatically

This improves security and prevents direct bucket access.

---

## 📂 Project Structure

```
.
├── .github/workflows
├── backend/lambda
├── frontend
├── infra/terraform
├── gigs
└── README.md
```

---

## 🚀 Deployment Steps (Summary)

1. Configure AWS CLI  
   ```
   aws configure
   ```

2. Create S3 bucket and DynamoDB table for Terraform backend

3. Run:
   ```
   terraform init
   terraform validate
   terraform plan
   ```

4. Push code to GitHub:
   ```
   git push origin main
   ```

GitHub Actions will handle the deployment automatically.

---

## 🧠 What I Learned From This Project

- How to write Terraform for AWS infrastructure
- How to configure remote backend (S3 + DynamoDB)
- How to automate deployments using GitHub Actions
- How to build serverless applications using Lambda
- How to debug errors using CloudWatch logs
- How to manage IAM roles securely
- How to fix large file issues in Git (.terraform folder)

---

## ⚠ Challenges I Faced

- S3 bucket name must be globally unique
- Terraform backend setup errors
- Lambda zip packaging mistakes
- API Gateway throttling limits
- Git large file push errors

---

## 📈 DevOps Concepts Demonstrated

- Infrastructure as Code
- CI/CD Automation
- Serverless Architecture
- Event-Driven Processing
- Monitoring and Logging
- Cloud Security Best Practices

---

## 🔮 Future Improvements

- Add user authentication (Cognito)
- Add DynamoDB for storing metadata
- Create separate Dev and Prod environments
- Add automated testing stage
- Add Docker-based local setup

---

## 👨‍💻 Author

Manish Singh Bora  
Aspiring DevOps Engineer  
Focused on AWS, Terraform, CI/CD, and Cloud Automation

---

⭐ If you like this project, feel free to give it a star!
