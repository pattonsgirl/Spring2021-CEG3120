# Project 4 - NOT FINALIZED

Initial setup.  For this project, you'll need access to a public repo.  I'm going to guess that your class repo may not be in a state where it should be made public, so in Pilot you will find a new invite link to a public repo for this course.  This project will be different from the rest - you are not required to complete milestones on time.  However, given that this is a huge project, you should use the milestones to set goals for yourself.

## Part 1:  Milestone due 4/9
Setup public repo via link in Pilot
Dockerize your website and test locally
    - https://www.docker.com/products/docker-desktop
    - https://www.docker.com/sites/default/files/d8/2019-09/docker-cheat-sheet.pdf
Add site content & Dockerfile to repo

## Part 2: Milestone due 4/16
Set up with AWS CodeBuild, have return status be used of whether of not Dockerfile could be built.

## Part 3: Milestone due 4/23
If success, get AWS AMI credentials (GitHub Secrets), upload container to ECR

## Part 4: Milestone due 4/23
Update ECS to use new container


## Extra Credit:
Dockerize your python bot
- Will require use of GitHub Secrets to protect the API key
- This guide has a parallel example with some things to consider
    - https://aws.amazon.com/blogs/containers/create-a-ci-cd-pipeline-for-amazon-ecs-with-github-actions-and-aws-codebuild-tests/
