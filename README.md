📬 **Serverless Contact Form on AWS**


**B — Build**

I built a fully serverless contact form backend on AWS using Infrastructure as Code (CloudFormation).
The system exposes a REST API that accepts form submissions, stores them in DynamoDB, and sends notifications via SNS — without managing servers.

Core AWS services used:

Amazon API Gateway

AWS Lambda

Amazon DynamoDB

Amazon SNS

AWS CloudFormation

AWS IAM

Amazon CloudWatch

**U — Use Case**

This project simulates a real-world contact form backend commonly used in production web applications.

What it does:

Accepts user contact form submissions

Persists data reliably

Sends notifications automatically

Scales without infrastructure management

Typical use cases:

Portfolio websites

Business contact forms

Event registrations

Serverless backend APIs

**I — Implementation**

All resources are provisioned using AWS CloudFormation, ensuring repeatable and consistent deployments.

Architecture Flow

Client sends a POST request to /submit

API Gateway triggers a Lambda function

Lambda:

Stores the submission in DynamoDB

Publishes a notification to SNS

CloudWatch logs execution and errors

API Endpoint

POST /submit

Sample Request

{
  "name": "Test User",
  "email": "test@example.com",
  "message": "This is a test message"
}


Successful Response

{
  "message": "Form submitted successfully"
}


Status Code: 200 OK

**L — Learning Outcomes**

This project strengthened my hands-on experience with:

Serverless architecture design

CloudFormation (Infrastructure as Code)

IAM least-privilege permissions

Debugging AccessDenied and runtime errors

API Gateway ↔ Lambda integrations

DynamoDB data modeling

CloudWatch logging and troubleshooting

I also practiced diagnosing real AWS issues such as:

IAM permission errors

Lambda execution failures

API Gateway 5xx responses

**D — Deployment & Validation**

✔ CloudFormation stack completed successfully (CREATE_COMPLETE)
✔ API Gateway returns 200 OK
✔ Lambda executes without errors
✔ DynamoDB stores submitted records
✔ SNS publishes notifications
✔ CloudWatch logs confirm end-to-end flow

The entire backend can be redeployed from the template with no manual setup.

🔐 Security

Lambda execution role uses least-privilege IAM permissions

Only required actions are allowed:

dynamodb:PutItem

sns:Publish

No hardcoded credentials

📌 Why This Project Matters

This project reflects real AWS workloads used in cloud and DevOps roles.
It demonstrates the ability to:

Build scalable serverless systems

Automate infrastructure

Troubleshoot AWS services

Apply security best practices
