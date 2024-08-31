# Fine Tuning Large Language Models (LLMs) on Amazon SageMaker

## Project Overview

This project demonstrates the fine-tuning of a Large Language Model (LLM) using multiple datasets to enhance its performance. The model is deployed using an Amazon SageMaker endpoint, enabling easy integration with other AWS services.

### Architecture Diagram
Below is the architecture diagram visual representation of the setup and illustrates the various AWS services involved in this project

![Architecture Diagram](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/Architecture%20Diagram%202.jpeg?raw=true
)

## Architecture Diagram Core Aspects:


- **Services Used:** 
  - Amazon Simple Storage Service (S3)
  - AWS Lambda
  - Amazon API Gateway
  - Amazon CloudFront
  - Amazon SageMaker
  - Amazon Jupyter Notebook
  - AWS Management Console
  - Sample Web Application

### Skills Demonstrated
- AWS Lambda Functions
- API Gateway Integration
- CloudFront Distribution
- Fine-tuning LLMs on SageMaker
- Model Tracking with SageMaker

## Architecture and Design

### Architecture Type
The architecture follows a serverless model using AWS managed services, ensuring scalability and high availability. Key components include:

- **Amazon S3** for storing datasets, model artifacts, and static web content.
- **Amazon SageMaker** for model training, fine-tuning, and deployment.
- **Amazon API Gateway** for routing API requests to AWS Lambda.
- **AWS Lambda** for processing requests and interfacing with the SageMaker endpoint.
- **Amazon CloudFront** for distributing the web application content globally.
  

## Setup and Installation Instructions

### Prerequisites
1. **AWS Account:** Ensure you have an active AWS account with appropriate permissions.
2. **AWS CLI:** Install and configure the AWS CLI on your local machine.
3. **SageMaker Notebook Instance:** Set up an Amazon SageMaker notebook instance.

### Step-by-Step Instructions

1. **Setup SageMaker Notebook:**
   - Create a new notebook instance in SageMaker.
   - Install necessary libraries such as Hugging Face Transformers and PyTorch.
   - Check the GPU memory to ensure compatibility with your model.

2. **Prepare Training Dataset:**
   - Upload your datasets to an S3 bucket.
   - Access the datasets from the SageMaker notebook for preprocessing.

3. **Load Pre-trained LLM:**
   - Import the pre-trained model `databricks/dolly-v2-3b` from Hugging Face.
   - Initialize the tokenizer and base model.

4. **Fine-Tune the LLM:**
   - Define the training parameters and use the SageMaker `Trainer` API to fine-tune the model.
   - Save the fine-tuned model artifacts back to S3.

5. **Deploy the Model:**
   - Use SageMaker to deploy the fine-tuned model as an endpoint.
   - Store the endpoint details for later use.

6. **Setup Web Application:**
   - Deploy a static web application on Amazon S3.
   - Use CloudFront to distribute the web application globally.

7. **Configure API Gateway and Lambda:**
   - Set up API Gateway to handle incoming API requests.
   - Create a Lambda function that invokes the SageMaker endpoint and processes the response.

## Testing and Validation

### Testing Steps

1. **Test the Deployed Endpoint:**
   - Use the SageMaker notebook to send test requests to the deployed endpoint.
   - Validate the model's performance with sample inputs.

2. **Web Application Testing:**
   - Access the web application through the CloudFront URL.
   - Send requests via the application to test the full flow from the front end to the backend Lambda function.

3. **API Gateway and Lambda Validation:**
   - Ensure that API Gateway correctly routes requests to the Lambda function.
   - Validate that the Lambda function correctly processes the requests and returns accurate responses from the model.

### Validation Methods
- Compare model outputs against expected results.
- Monitor logs in CloudWatch for any errors during API requests.
- Use A/B testing to compare performance metrics before and after fine-tuning.

## Output Indicator

The final deliverables include:
- **Fine-tuned Model:** Available in an S3 bucket.
- **Deployed Model Endpoint:** Accessible via API Gateway.
- **Web Application:** Hosted on S3 and distributed via CloudFront.
- **Project Documentation:** This GitHub Markdown file detailing the project setup, architecture, and testing.
