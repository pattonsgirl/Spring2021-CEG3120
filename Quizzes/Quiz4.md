# Quiz 4

1. Recommend me a base Docker image for python 3 such that I can run:
docker pull ____
Hint: https://hub.docker.com/_/python
    - python

2. I have a docker image named sprouts:3.5  It runs a service over port 42.  Write a docker run command that will use this image and bind it to the host / local port 5000.
    - docker run -p 5000:42 sprouts:3.5
    - docker run -d -p 5000:42 sprouts:3.5

3. In GitHub Action workflows, an ____ defines when the workflow triggers - upon push, release, etc
    - events
    - also accepted "on" although that is technically syntax ;)

4. I have an API key that my application needs to use, but it can't exist publicly in the project repository.  Describe a solution to investigate.
    - .gitignore
    - GitHub secrets
    - Docker can also be used to host secrets

5. T/F By putting my container image in a repository, such as ECR, I can now pull it to resources I want to deploy it to, such as ECS or even my local machine.
    - True

6. (Bonus) In the AWS CLI, write a command that will show images in an ECR repository named veggies/tomatoes in region us-west-1
    - aws ecr describe-images --repository-name veggies/tomatoes --region us-west-1