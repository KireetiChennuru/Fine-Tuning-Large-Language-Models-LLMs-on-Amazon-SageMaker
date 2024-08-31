# Fine Tuning Large Language Models (LLMs) on Amazon SageMaker

## Project Overview

This project demonstrates the fine-tuning of a Large Language Model (LLM) using multiple datasets to enhance its performance. The model is deployed using an Amazon SageMaker endpoint, enabling easy integration with other AWS services.

### Architecture Diagram
Refer to the architecture diagram visual representation of the setup and illustrates the various AWS services involved in this project

![Architecture Diagram](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/Architecture%20Diagram%202.jpeg?raw=true
)

## Inputs

- **Customer Objective:** Use internal data to fine-tune Generative AI models, specifically Large Language Models (LLMs), to improve their performance on specific NLP tasks.
- **Fine Tuning:** Fine-tuning, also known as transfer learning, allows the adaptation of a pre-trained model to a specific problem domain, saving computational resources.
- **NLP Tasks:** LLMs can be applied to various NLP tasks such as text generation, sentiment analysis, language translation, and question-answering systems.

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

### Step-by-Step Instructions

1. **Setup SageMaker Notebook:**
   - Create a new notebook instance in SageMaker.
   - Install necessary libraries such as Hugging Face Transformers and PyTorch.
   - Check the GPU memory to ensure compatibility with your model.
     
![Setup SageMaker Notebook](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/Fine%20tuning%20-%20Check%20GPU%20Memory%20.png?raw=true)


2. **Prepare Training Dataset:**
   - Load and pre-process the SageMaker FAQ data to ensure it's in the right format for training. This step is crucial for setting the foundation of the fine-tuning process.
   - Upload the pre-processed datasets to an S3 bucket.
     
  ![Prepare Training Dataset](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/Fine%20tuning%20-%20Import%20Libraries.png?raw=true)
   ![Prepare Training Dataset](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/Fine%20tuning%20-%20Preparing%20the%20training%20dataset.png?raw=true)

3. **Load Pre-trained LLM:**
   - Import the pre-trained model `databricks/dolly-v2-3b` from Hugging Face.
   - Initialize the tokenizer and base model.

  ![Load Pre-trained LLM](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/Fine%20tuning%20-%20Load%20a%20pre-trained%20LLM.png?raw=true)


4. **Fine-Tune the LLM:**
   - Define the training parameters and use the SageMaker `Trainer` API to fine-tune the model. This process adapts the model to the specific data provided by the customer.
   - Save the fine-tuned model artifacts back to S3.

  ![Architecture Diagram](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/Architecture%20Diagram%202.jpeg?raw=true


5. **Test the Fine-Tuned LLM:**
   - Test the fine-tuned LLM on a validation dataset to assess its performance. This step ensures the model is performing as expected and is ready for deployment.
   - Address any issues or make necessary refinements.

  ![Architecture Diagram](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/Architecture%20Diagram%202.jpeg?raw=true


6. **Deploy the Model:**
   - Deploy the fine-tuned LLM to a SageMaker endpoint.
   - Store the model artifacts in an S3 bucket for future reference.
  
  ![Deploy the Model](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/Fine%20tuning%20-%20Deploy%20the%20Fine%20tune%20model.png?raw=true)
  ![Deploy the Model](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/Fine%20tuning%20-%20Test%20the%20deployed%20inference%20.png?raw=true)

7. **Configure API Gateway and Lambda:**
   - Write an AWS Lambda function to interface with the SageMaker endpoint. This function handles the input and output formats and serves as a bridge between the Amazon API Gateway and the LLM.
   - Configure API Gateway to create a RESTful API for the Lambda function, exposing the LLM functionality to external applications securely.
  
  ![Configure API Gateway and Lambda](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/API%20gateway%20-%20Stages.png?raw=true)
  ![Configure API Gateway and Lambda](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/Lambda%20Endpoint%20test%20function.png?raw=true)

8. **Web Application:**
   - Use CloudFront to distribute the web application globally.
  
  ![Web Application](https://github.com/KireetiChennuru/Fine-Tuning-Large-Language-Models-LLMs-on-Amazon-SageMaker/blob/main/Project_Files/CloudFront%20Distributions.png?raw=true)



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


