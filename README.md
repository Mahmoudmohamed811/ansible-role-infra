# Infra Role

This role provisions AWS infrastructure using CloudFormation. It creates a CloudFormation stack based on a provided template and sets facts for the stack outputs (e.g., VPC ID, Subnet IDs, Security Group IDs).

## Requirements

- **Ansible**: Version 2.9 or higher.
- **AWS Credentials**: Configured on the target machine (e.g., using `aws configure` or environment variables).
- **Python Dependencies**:
  - `boto3` and `botocore` (required for AWS modules).
  - Install them using:
    ```bash
    pip install boto3 botocore
    ```
- **Ansible Collections**:
  - `amazon.aws` (for AWS modules).
  - Install it using:
    ```bash
    ansible-galaxy collection install amazon.aws
    ```

## Role Variables

### Default Variables (defined in `defaults/main.yml`)
- `stack_name`: The name of the CloudFormation stack. Default: `"MyInfrastructure"`.
- `aws_region`: The AWS region where the stack will be created. Default: `"us-east-1"`.
- `vpc_cidr`: The CIDR block for the VPC. Default: `"10.0.0.0/16"`.
- `vpc_name`: The name tag for the VPC. Default: `"MyVPC"`.
- `public_subnet_cidr`: The CIDR block for the public subnet. Default: `"10.0.1.0/24"`.
- `private_subnet1_cidr`: The CIDR block for the first private subnet. Default: `"10.0.2.0/24"`.
- `private_subnet2_cidr`: The CIDR block for the second private subnet. Default: `"10.0.3.0/24"`.
- `web_sg_name`: The name of the security group for web servers. Default: `"WebSecurityGroup"`.
- `db_sg_name`: The name of the security group for the database. Default: `"DBSecurityGroup"`.
