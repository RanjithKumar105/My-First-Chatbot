AI-Powered-Health-Assistant-Using-LLMs-LangChain-Pinecone-Flask-AWS

🚀 How to Get Started
1. Clone the Repository
git clone https://github.com/your-username/AI-Powered-Health-Assistant.git

2. Set up a Conda Environment
conda create -n healthbot python=3.10 -y

conda activate healthbot

3. Install Project Dependencies
pip install -r requirements.txt

4. Configure Environment Variables

Create a .env file in the project root and include your Pinecone and OpenAI credentials:

PINECONE_API_KEY="your_pinecone_api_key"
OPENAI_API_KEY="your_openai_api_key"

5. Build the Vector Index

Run the following command to push embeddings to Pinecone:

python build_index.py

6. Launch the Application
python app.py


Now open your browser and navigate to:

http://127.0.0.1:5000/

🛠️ Tech Stack

Python 3.10

LangChain for orchestration

Flask as the backend framework

LLMs (GPT-based models) for conversation

Pinecone for vector storage

🚢 AWS CI/CD Deployment with GitHub Actions
Step 1: Login to AWS Console
Step 2: Create IAM User for Deployment

Grant the following permissions:

EC2 Access – to manage virtual servers

ECR Access – to store Docker images

Policies to attach:

AmazonEC2FullAccess

AmazonEC2ContainerRegistryFullAccess

Step 3: Create an ECR Repository

Example URI:

123456789012.dkr.ecr.us-east-1.amazonaws.com/health-assistant

Step 4: Launch an EC2 Instance (Ubuntu)
Step 5: Install Docker on EC2
sudo apt-get update -y
sudo apt-get upgrade -y
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker

Step 6: Configure EC2 as a Self-Hosted Runner

Go to:
GitHub Repo > Settings > Actions > Runners > New Self-Hosted Runner

Follow the commands provided for Ubuntu.

Step 7: Add GitHub Secrets

AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

AWS_DEFAULT_REGION

ECR_REPO

PINECONE_API_KEY

OPENAI_API_KEY

✅ You now have a complete pipeline: code → Docker image → pushed to ECR → deployed on EC2 via GitHub Actions
