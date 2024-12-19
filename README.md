# interview-project
# Project: Mid-Level DevOps Technical Assessment

## Objective
Deploy a simple API that returns the current server time to AWS Elastic Container Service (ECS) using Terraform. Optionally, implement a Continuous Integration/Continuous Deployment (CI/CD) pipeline using Jenkins.

## Repository Structure
```
|-- app.py                  # Flask application source code
|-- provider.tf             # Terraform provider configuration
|-- vpc.tf                  # VPC, subnets, and networking setup
|-- ecs.tf                  # ECS, ALB, and security group setup
|-- Jenkinsfile             # Jenkins CI/CD pipeline
```

## Steps to Deploy

### 1. Clone the Repository
```bash
git clone https://github.com/Angecalais97/interview.git
cd interview
```

### 2. Build and Test Flask Application
Run the Flask application locally to ensure it's working:
```bash
python3 app.py
```
Access it at `http://localhost:5000` to see the server time.

### 3. AWS Terraform Setup
Ensure you have AWS credentials and Terraform installed.

#### Initialize Terraform
```bash
terraform init
```

#### Apply Terraform Configuration
```bash
terraform apply -auto-approve
```

### 4. Jenkins CI/CD Pipeline
Ensure you have Jenkins installed and configured.

#### Add Pipeline
1. Create a new Jenkins pipeline.
2. Copy the `Jenkinsfile` content into the pipeline script.

#### Run the Pipeline
Trigger the pipeline to:
1. Build and push the Docker image to AWS ECR.
2. Deploy the application using Terraform.

### 5. Access the Application
Retrieve the load balancer DNS from Terraform outputs:
```bash
terraform output load_balancer_dns
```
Visit the DNS to see the deployed Flask app.

## Key Points for Interview
- **Flask Application**: Demonstrates simple API functionality.
- **Terraform Modules**: Used for modular infrastructure code.
- **AWS Services**: Covers ECS, ALB, and secure networking.
- **CI/CD Pipeline**: Automated using Jenkins for efficiency.

### FAQs
1. **Why Flask?**
   Flask is lightweight and suitable for creating APIs quickly.

2. **Why Terraform?**
   It provides infrastructure as code, ensuring consistency and scalability.

3. **How is the infrastructure secured?**
   Security groups and VPC ensure controlled access.

4. **What are the CI/CD benefits?**
   Automates deployment, reducing manual errors and improving delivery speed.

---
Feel free to ask more questions during the interview for further clarification.
