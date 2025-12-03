main.tf 
```
# -----------------------------
# Security Group
# -----------------------------
resource "aws_security_group" "ec2_sg" {
  name        = "amazon_clone_sg"
  description = "Allow all inbound traffic"
  vpc_id      = "vpc-00d439279df61f6de"

  ingress {
    description = "Allow ALL inbound traffic"
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    description = "Allow all outbound traffic"
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }

  tags = {
    Name = "amazon-clone-security-group"
  }
}

# -----------------------------
# EC2 Instance
# -----------------------------
resource "aws_instance" "amazon_clone_instance" {
  ami           = var.ami_id
  instance_type = var.instance_type
  subnet_id     = "subnet-0463631125b5d1cca"
  key_name      = var.key_name

  vpc_security_group_ids = [
    aws_security_group.ec2_sg.id
  ]

  associate_public_ip_address = true

  tags = {
    Name = "amazon-clone-ec2"
  }
}

```

variable.tf
```
variable "region" {
  type    = string
  default = "eu-north-1"
}

variable "instance_type" {
  type    = string
  default = "t3.medium"
}

variable "ami_id" {
  type    = string
  default = "ami-0f50f13aefb6c0a5d"
}

variable "key_name" {
  type    = string
  default = "jenkins-key"
}

```
provider.tf
```
provider "aws" {
 region = "eu-north-1"
 profile = "tf-user"
}

```
