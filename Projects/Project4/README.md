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

    

## Part 3: Milestone due 4/23
- Add ECS components to workflow
- TODO: Add milestone deliverables, namely documentation requirements.

## Extra Credit:
- Dockerize your python bot
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