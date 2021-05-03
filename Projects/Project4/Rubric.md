# Project 4 Rubric

## Part 1 - Setup repo contents
- Repo contents:
    - Dockerfile
    - Site content (stand alone or in http folder)

## Part 2 - Deploy to container repository
- AWS CLI + ECR + GitHub Actions
- DockerHub + GitHub Actions

## Part 3
### Documentation requirements using ECR
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

### Documentation requirements using DockerHub
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
    - Create DockerHub public repo
        - process to create
    - Configure GitHub Secrets
        - what credentials are needed - DockerHub credentials (do not state your credentials)
        - set secrets and secret names
    - Configure GitHub Workflow
        - variables to change (repository, etc.) 


## Milestone Submission Extra Credit
- 4/9: Dockerfile
- 4/16: GitHub Actions + ECR
- 4/23: Documentation

## Extra Credit - Docker Pull
- Documentation to perform the following:
    - How to pull image with `docker pull`, what repo is the image in, requirements of the repo (public vs. private)
    - Run the pulled image locally, using your system or a system on AWS as the host.

## Extra Credit - [Docke]Rise of the Discord Bot
- Dockerize your python bot - place in repo in folder named `Discord-Bot`
    - Add instructions to handle API key from Discord.  Maybe have a docker copy that gets a .env file from their path (this need to exist to build and run image)
    - Your API key may be the most challenging piece of this project extra credit.  GitHub secrets might be handy.
    - Be sure to site your sources if you model off of an example / other documentation