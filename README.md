# Terraform Multi-Environment Infrastructure

This repository provides a structured approach to provisioning and managing AWS infrastructure across multiple environments—Development, Staging, and Production—using Terraform. It emphasizes modularity and reusability, ensuring consistent deployments across different stages of the application lifecycle.

---

## 📁 Project Structure

The repository is organized as follows:

.
├── environments/
│ ├── dev/
│ ├── stg/
│ └── prod/
└── modules/
└── aws_infra/
├── main.tf
├── variables.tf
└── outputs.tf

yaml
Copy
Edit

* **environments/**: Contains environment-specific configurations. Each subdirectory (`dev`, `stg`, `prod`) includes Terraform files tailored for that environment.
* **modules/aws_infra/**: Houses reusable Terraform modules that define the core AWS infrastructure components.

---

## 🚀 Features

* **Multi-Environment Support**: Isolated configurations for Development, Staging, and Production environments.
* **Modular Design**: Promotes reusability and maintainability through Terraform modules.
* **AWS Resources Provisioning**:
  * **EC2 Instances**: Launches instances with environment-specific settings.
  * **S3 Buckets**: Creates buckets with appropriate tagging and access controls.
  * **DynamoDB Tables**: Sets up tables using the `PAY_PER_REQUEST` billing mode.
  * **VPC and Security Groups**: Establishes networking components to ensure secure and efficient communication.
* **Key Pair Management**: Facilitates secure SSH access to EC2 instances via AWS key pairs.

---

## 🔧 Prerequisites

Before deploying the infrastructure, ensure the following tools are installed and configured:

* **Terraform**: Version 1.0 or higher.
* **AWS CLI**: Configured with credentials having sufficient permissions.
* **SSH Key Pair**: For accessing EC2 instances.

---

## 🛠️ Usage

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/Aarush-Gupta15/Teraform_task.git
   cd Teraform_task
Generate SSH Key Pair (if not already available):

bash
Copy
Edit
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
Ensure the public key is added to AWS EC2 Key Pairs.

Navigate to Desired Environment:

bash
Copy
Edit
cd environments/dev   # Replace 'dev' with 'stg' or 'prod' as needed
Initialize Terraform:

bash
Copy
Edit
terraform init
Review and Apply Configuration:

bash
Copy
Edit
terraform plan
terraform apply
Confirm the prompt to proceed with the infrastructure deployment.
