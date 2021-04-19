# Project 4 

For this project, you'll need access to a public repo.  I'm going to guess that your class repo may not be in a state where it should be made public (remember those Discord API keys?), so in Pilot you will find a new invite link to a public repo for this course.  Completion of each milestone **by the date specificied for the milestone** will get you 1 pt of extra credit per milestone met.  To qualify, you must submit your project to the Dropbox for Project 4 in Pilot.

## Setup:
- Create public repo per link in Pilot
- Clone repo to your working environment (you should not need to use EC2 instances).
- Install [Docker for Desktop](https://www.docker.com/products/docker-desktop) 
- Maybe: Install [AWS CLI](https://aws.amazon.com/cli/) and [configure](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html)

## Part 1: Dockerize it - Milestone due 4/9
- Setup public repo via link in Pilot
- Dockerize your website and test locally
    - https://www.docker.com/sites/default/files/d8/2019-09/docker-cheat-sheet.pdf
    - Your website is in reference to last project, where you put an `index.html` page on a server running `apache2`
        - As per before, a template html page is posted here in the project folder [index.html](index.html) 
- Add site content & Dockerfile to repo

## Part 2: GitHub Actions & ECR - Milestone due 4/17
- Instructions to configure AWS CLI: https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html
    - You will need AWS CLI so that you can interact with an account that _can_ use ECR and ECS (I disabled your ability to log into the web interface using these credentials)
    - Credential notes are located in Pilot -> Content -> Projects
    - Create ECR Repository from CLI:
        - Replace `w###aaa` with your w# so we can tell things apart
        - `aws ecr create-repository --repository-name ceg3120/w###aaa --region us-east-1`
- Create GitHub Actions secrets named AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY using info in Pilot page.
- Set up GitHub workflow that pushes image to ECR, comment out ECS related sections
    - Using workflow templated here: https://docs.github.com/en/actions/guides/deploying-to-amazon-elastic-container-service

## Part 3: Documentation - Milestone due 4/23

- Create `README.md` in main folder of your repo that details the following:
    - Project Overview
    - Run Project Locally
        - how you installed docker + dependencies (WSL2, for example)
        - how to build the container
        - how to run the container
        - how to view the project (open a browser...go to ip and port...)
    - Configure AWS CLI
        - need AWS IAM user with admin credentials
        - how you installed
        - how to configure
    - Create ECR
        - command to create
    - Configure GitHub Secrets
        - need AWS IAM user with admin credentials
        - set secrets and secret names
    - Configure GitHub Workflow
        - variables to change (AWS_REGION, etc.)    

## Extra Credit - Docker Pull
- https://docs.aws.amazon.com/AmazonECR/latest/userguide/registry_auth.html
- https://docs.aws.amazon.com/AmazonECR/latest/userguide/docker-pull-ecr-image.html
- Pull image, run locally


## Extra Credit - [Docke]Rise of the Discord Bot
- Dockerize your python bot - place in repo in folder named `Discord-Bot`
    - Your API key may be the most challenging piece of this project extra credit.  GitHub secrets might be handy.
    - Be sure to site your sources if you model off of an example / other documentation

## Submission

In your GitHub repository, select the green `Code` button then select `Download ZIP`. Upload this zip file to Pilot.

In the `Comment` area in the Pilot Dropbox, copy URL / link to the repository corresponding to the project you are submitting

## Documenting Rabbit Holes
This section is notes on what has needed to be modified over the course of this project.
- Cannot authenticate on AWS CLI with EDU account credentials
        - You can't make an IAM user, so you'll need to pull up yours, see below
    - How to get IAM user credentials
        - Sign in to AWS Educate, click our classroom - don't click AWS Console
        - Click other blue button for account details.  In here, you'll find the credentials for AWS CLI
    - Guide update incoming
- Verify services are actually available before using again: 
    - https://awseducate-starter-account-services.s3.amazonaws.com/AWS_Educate_Starter_Account_Services_Supported.pdf

- Using this as resource created below: https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-cli-tutorial-ec2.html
- ~~Create EC2 Key Pair~~ - if using EC2 Deployment
    - Remember, you're on my AWS, so you'll need this key for a future step - specifically remember the key-name value
    - `aws ec2 create-key-pair --key-name w###aaa --query 'KeyMaterial' --output text > aws-w###aaa.pem`
    - Change permssions: `chmod 400 aws-w###aaa.pem`
- ~~Create ECS cluster~~ - if using EC2 Deployment
    - `ecs-cli configure --cluster cluster-w###aaa --default-launch-type EC2 --config-name cluster-w###aaa --region us-east-1`
    - `ecs-cli up --keypair w###aaa --capability-iam --size 2 --instance-type t2.small --cluster-config cluster-w###aaa`
        - If you mess up and need to re-run, add `--force` at the end of the command to have it replace the old with the new
    - What about security groups and ports?
        - By default, the security group created for your container instances opens port 80 for inbound traffic
        - Convenient, moving on.  If this was not the case, would need `--security-group` parameter and set additional options

- Install ECS CLI Tools (this is in addition to AWS CLI)
    - [Link to install guide](https://docs.amazonaws.cn/en_us/AmazonECS/latest/developerguide/ECS_CLI_installation.html)
    - Linux commands:
        - `sudo curl -Lo /usr/local/bin/ecs-cli https://s3.cn-north-1.amazonaws.com.cn/amazon-ecs-cli/ecs-cli-linux-amd64-latest`
        - `sudo chmod +x /usr/local/bin/ecs-cli`
- Create ECS cluster
    - `ecs-cli configure --cluster ecs-w###aaa --default-launch-type FARGATE --config-name ecs-w###aaa --region us-east-1`
    - `ecs-cli up --cluster-config ecs-w###aaa`
- Create ECS service
- Create ECS Task Definition
- Modify workflow to use GitHub Actions to auto deploy
- In your workflow, `ECS_CLUSTER` = ecs-w###aaa per what you created above