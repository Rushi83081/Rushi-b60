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



Step 1 — Clone the Repository

Open your terminal or Codespace:

# Clone the repo
git clone https://github.com/abhipraydhoble/Project-Amazon-Clone.git

# Go into the project folder
cd Project-Amazon-Clone

Step 2 — Install Dependencies

Check the project folder for package.json (Node.js project). Then run:

npm install


This installs all required packages for the project.

Step 3 — Run the Project Locally
# Start the project
npm start


Open your browser at http://localhost:3000 (or the port shown in terminal).

You should see the Amazon Clone UI.

Step 4 — Test the App

Browse products, add to cart, check out (if backend is connected).

Make sure everything works as expected.

Step 5 — Push to Your Repository
# Initialize git if this is a new repo
git init

# Add all files
git add .

# Commit changes
git commit -m "Add Amazon Clone project with setup instructions"

# Add your repository as remote
git remote add origin <YOUR_REPO_URL>

# Push to GitHub
git branch -M main
git push -u origin main
