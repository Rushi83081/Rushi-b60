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


1. Install Required Tools (Ubuntu)
Install AWS CLI
sudo apt update
sudo apt install awscli -y
Install Terraform
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update
sudo apt install terraform -y

2. Configure AWS CLI
Run:

aws configure
Enter:

Access Key
Secret Key
Region
Output: json

3. Clone the Repository
mkdir amazon
cd amazon
git clone https://github.com/abhipraydhoble/Project-Amazon-Clone.git
ls
Move into Terraform folder:

cd Project-Amazon-Clone/JENKINS-TF

4. Update Terraform Files
provider.tf
Set your AWS region:

region = "ap-south-1"
main.tf
Update:

ami
instance_type (ex: t2.micro, t3.medium)
📌 5. Deploy Infrastructure
terraform init
terraform validate
terraform plan
terraform apply --auto-approve
This creates:

Jenkins EC2 Server
Security Groups
Required networking
📌 6. Login to Jenkins Server
Get EC2 Public IP → open browser:

http://<PUBLIC-IP>:8080
Get Jenkins admin password:

sudo cat /var/lib/jenkins/secrets/initialAdminPassword
Paste into browser → login.

📌 7. Install Required Jenkins Plugins
Install:

Eclipse Temurin Installer
SonarQube Scanner
NodeJS Plugin
OWASP Dependency Check
Prometheus Metrics
Docker (ALL options + CloudBees)
Stage View
📌 8. Configure Credentials in Jenkins
Sonar Token
Open Sonar:

http://<instance-ip>:9000
Go to: Administration → Security → Tokens
Generate token: sonar-token

Add in Jenkins:

Manage Jenkins → Credentials
Add Secret Text
ID: sonar-token
Docker Hub Credentials
Add:

Username
Password
ID: docker
📌 9. Configure Tools (Manage Jenkins → Tools)
JDK
Name: jdk17
Install from adoptium
Version: 17
NodeJS
Name: node16
Version: 16.2.0
Sonar Scanner
Default settings
Docker
Install via Jenkins installer
📌 10. SonarQube Integration in Jenkins
Manage Jenkins → System
Add:

SonarQube Server
Token ID: sonar-token

11. Jenkins Pipeline Script
Replace <YOUR-DOCKER-USERNAME> with your Docker Hub username.

pipeline{
    agent any
    tools{
        jdk 'jdk17'
        nodejs 'node16'
    }
    environment {
        SCANNER_HOME=tool 'sonar-scanner'
    }
    stages {
        stage('clean workspace'){
            steps{
                cleanWs()
            }
        }
        stage('Checkout from Git'){
            steps{
                git branch: 'main', url: 'https://github.com/abhipraydhoble/Project-Amazon-Clone.git'
            }
        }
        stage("Sonarqube Analysis "){
            steps{
                withSonarQubeEnv('sonar-server') {
                    sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Amazon \
                    -Dsonar.projectKey=Amazon '''
                }
            }
        }
        stage("quality gate"){
           steps {
                script {
                    waitForQualityGate abortPipeline: false, credentialsId: 'jenkins' 
                }
            } 
        }
        stage('Install Dependencies') {
            steps {
                sh "npm install"
            }
        }
        stage('OWASP FS SCAN') {
            steps {
                dependencyCheck additionalArguments: '--scan ./ --disableYarnAudit --disableNodeAudit', odcInstallation: 'DP-Check'
                dependencyCheckPublisher pattern: '**/dependency-check-report.xml'
            }
        }
        stage('TRIVY FS SCAN') {
            steps {
                sh "trivy fs . > trivyfs.txt"
            }
        }
        stage("Docker Build & Push"){
            steps{
                script{
                   withDockerRegistry(credentialsId: 'docker', toolName: 'docker'){   
                       sh "docker build -t amazon-clone ."
                       sh "docker tag amazon-clone <YOUR-DOCKER-USERNAME>/amazon-clone:latest"
                       sh "docker push <YOUR-DOCKER-USERNAME>/amazon-clone:latest"
                    }
                }
            }
        }
        stage("TRIVY"){
            steps{
                sh "trivy image <YOUR-DOCKER-USERNAME>/amazon-clone:latest > trivyimage.txt"
            }
        }
        stage('Deploy to container'){
            steps{
                sh 'docker run -d --name amazon-clone -p 3000:3000 <YOUR-DOCKER-USERNAME>/amazon-clone:latest'
            }
        }
    }
}
