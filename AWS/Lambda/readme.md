# 📘 AWS Lambda Practical

## 🟢 Step 1: Create IAM Role

**🔐 IAM → Roles → Create role**

✔ Service: Lambda

✔ Policy: AmazonEC2FullAccess

✔ Role name: Lambda-EC2-Role


## 🟢 Step 2: Create Lambda Function

☁️ Lambda → Create function

✔ Name: EC2-Start-Stop

✔ Runtime: Python 3.9

✔ Role: Lambda-EC2-Role


## 🟢 Step 3: Add EC2 START Code

💻 Lambda → Code tab

📌 Paste EC2 start code
```
import boto3

# Initialize the EC2 client
ec2 = boto3.client('ec2')

def lambda_handler(event, context):
    # Hardcoded EC2 instance ID
    instance_id = 'i-0a30a69aab79a1275'
    
    # Start the EC2 instance
    try:
        response = ec2.start_instances(InstanceIds=[instance_id])
        print(f'Starting instance {instance_id}')
        return f'Instance {instance_id} is starting'
    
    except Exception as e:
        print(f'Error starting instance {instance_id}: {str(e)}')
        return f'Error: {str(e)}'
```

✔ Click Deploy

**🧪 Test event:**
```
{ 
"action": "start"
}
```
▶️ Result: EC2 STARTS

## 🟢 Step 4: Add EC2 STOP Code

💻 Replace code with EC2 stop code

```
import boto3

# Initialize the EC2 client
ec2 = boto3.client('ec2')

def lambda_handler(event, context):
    # Hardcoded EC2 instance ID
    instance_id = 'i-0a30a69aab79a1275'
    
    # Stop the EC2 instance
    try:
        response = ec2.stop_instances(InstanceIds=[instance_id])
        print(f'Stopping instance {instance_id}')
        return f'Instance {instance_id} is stopping'
    
    except Exception as e:
        print(f'Error stopping instance {instance_id}: {str(e)}')
        return f'Error: {str(e)}'

```

✔ Click Deploy

**🧪 Test event:**
```
{ 
"action": "stop" 
}
```
⏹ Result: EC2 STOPS

## 🟢 Step 5: Verify

🖥️ EC2 Console

✔ Instance state changes:

* ▶️ Running

* ⏹ Stopped
