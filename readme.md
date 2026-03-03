
# MLflow on AWS

## MLflow on AWS Setup:

1. Login to AWS console.
2. Create IAM user with AdministratorAccess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create a s3 bucket
5. Create EC2 machine (Ubuntu) & add Security groups 5000 port

Run the following command on EC2 machine
```bash
sudo apt update

sudo apt install python3-pip

sudo apt install pipenv

sudo apt install virtualenv

mkdir mlflow

cd mlflow

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell


## Then set aws credentials if you are runing on vs code you can give in the terminal
aws configure


#Finally 
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-tracking-buc25 --allowed-hosts *

#open Public IPv4 DNS to the port 5000

Go to --> EC2 instance --> Security --> Security groups --> Edit inbound rules --> add rule
Custome TCP --- 5000 --- 0.0.0.0/0

then open the uri in http://....amazonaws.com:5000/

```
