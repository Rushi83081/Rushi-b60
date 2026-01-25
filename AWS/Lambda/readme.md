# 📘 AWS Lambda Practical – Start & Stop EC2 Instance

This practical demonstrates how to use **AWS Lambda** with an **IAM Role** to **start and stop an EC2 instance** using **Python (boto3)**.  
No access keys are used — permissions are handled securely using IAM roles.

---

## 🟢 Step 1: Create IAM Role for Lambda

Open AWS Console and navigate to:

IAM → Roles → Create role

### Role Configuration
- Trusted entity type: **AWS service**
- Use case: **Lambda**

### Attach the following policies
- AmazonEC2FullAccess  
- AWSLambdaBasicExecutionRole  
- AmazonLambda_FullAccess  

### Role Name

Lambda-EC2-Role


Click **Create role**

---

## 🟢 Step 2: Create Lambda Function

Navigate to:

AWS Lambda → Create function

### Function Details
- Function name: **EC2-Start-Stop**
- Runtime: **Python 3.9**
- Execution role: **Use an existing role**
- Existing role: **Lambda-EC2-Role**

Click **Create function**

---

## 🟢 Step 3: Add EC2 START Code

Go to:

Lambda → Function → Code tab

Paste the following code to **start the EC2 instance**:

```python
import boto3

# Initialize the EC2 client
ec2 = boto3.client('ec2')

def lambda_handler(event, context):
    # Hardcoded EC2 instance ID
    instance_id = 'i-0a30a69aab79a1275'
    
    try:
        ec2.start_instances(InstanceIds=[instance_id])
        print(f"Starting instance {instance_id}")
        return f"Instance {instance_id} is starting"
    
    except Exception as e:
        print(f"Error starting instance: {str(e)}")
        return f"Error: {str(e)}"
```

### Click Deploy

## Test the Function

### Create a test event with the following input:
```
{
  "action": "start"
}
```

▶️ Result: EC2 instance starts successfully

---

## 🟢 Step 4: Add EC2 STOP Code

### Replace the existing code with the EC2 stop code below:
```
import boto3

# Initialize the EC2 client
ec2 = boto3.client('ec2')

def lambda_handler(event, context):
    # Hardcoded EC2 instance ID
    instance_id = 'i-0a30a69aab79a1275'
    
    try:
        ec2.stop_instances(InstanceIds=[instance_id])
        print(f"Stopping instance {instance_id}")
        return f"Instance {instance_id} is stopping"
    
    except Exception as e:
        print(f"Error stopping instance: {str(e)}")
        return f"Error: {str(e)}"
```
### Click Deploy

## Test the Function

### Use the following test event:
```
{
  "action": "stop"
}
```

⏹ Result: EC2 instance stops successfully

---
## 🟢 Step 5: Verify EC2 Instance Status

### Navigate to:

EC2 Console → Instances

Verify the instance state:

- ▶️ Running (after start)

- ⏹ Stopped (after stop)
