# Project 4 

For this project, you'll need access to a public repo.  I'm going to guess that your class repo may not be in a state where it should be made public (remember those Discord API keys?), so in Pilot you will find a new invite link to a public repo for this course.  Completion of each milestone **by the date specificied for the milestone** will get you 1 pt of extra credit per milestone met.  To qualify, you must submit your project to the Dropbox for Project 4 in Pilot.

## Setup:
- Create public repo per link in Pilot
- Clone repo to your working environment (you should not need to use EC2 instances).
- Install [Docker for Desktop](https://www.docker.com/products/docker-desktop) 
- Maybe: Install [AWS CLI](https://aws.amazon.com/cli/)

## Part 1: Dockerize it - Milestone due 4/9
- Setup public repo via link in Pilot
- Dockerize your website and test locally
    - https://www.docker.com/sites/default/files/d8/2019-09/docker-cheat-sheet.pdf
    - Your website is in reference to last project, where you put an `index.html` page on a server running `apache2`
        - As per before, a template html page is posted here in the project folder [index.html](index.html) 
- Add site content & Dockerfile to repo

## Part 2: GitHub Actions & ECR - Milestone due 4/17
- Set up ECR on AWS educate account
- Create GitHub Actions secrets named AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY to store the values for your Amazon IAM access key
- Set up GitHub workflow that pushes image to ECR, comment out ECS related sections
    - Using workflow templated here: https://docs.github.com/en/actions/guides/deploying-to-amazon-elastic-container-service
- Optional: install AWS CLI and play with using commands to play with your AWS account

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
