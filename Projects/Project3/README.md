# Project 3

## Objectives

- Practice good documentation for a growing infrastructure
- Create a CloudFormation template for an infrastructure
- Explore distributed architecture via HAProxy

### AWS Educate Quick Link:

- [Sign in to AWS educate](https://www.awseducate.com/signin/SiteLogin)

## Load balancing with HAProxy

You are going to configure an environment per the following requirements.  Note that you can start by creating everything manually, but part of your deliverables will be a CloudFormation template that stands this layout up.

- Stand up one proxy server (HAProxy)
- Stand up two apache or nginx servers
- Place a different `index.html` on the HTTP servers
  - You can use mine in the Project folder
  - You can use your own content if you wish - developing the page / site is not a core part of this class
- Configure the HAProxy server to balance requests between the two web servers
  - Use Layer 4 balancing for this set up
- Security groups should be changed to the following rules:
  - Port 80 traffic from external - this should be world accessible
  - Port 22 traffic from external - you can make this just your IP address
  - Port 80 traffic in private subnet
  - Port 22 traffic in private subnet

### Deliverables

1. In your `AWS` folder in your repository, have your CloudFormation template that is used to create the infrastructure detailed above.  Note that you can start by creating everything manually, you must also have a CloudFormation template that stands this layout up.  Your template should also install the basic packages needed by each system.
  - [cf-template.yml] is a reference template that sets up a VPC, subnet, security group rules and reserves one EIP and creates on EC2 instance.
  - Changes needed:
    - 3 EIPs instead of 1
    - 3 EC2 instances instead of 1
      - Changes to the package list per what software needs to be installed where
    - Changes to Security Group rules
    - Changes to AMI
    - Appropraite naming conventions

2. In your `AWS` folder in your repository, create a file called `proxy-config.md`.  In this file document how you configured the proxy and webservers.  Note which configuration files were modified and the purpose of modifying them.
  - **_HAProxy configuration documentation requirements_**
    - What software / service needed to be installed
    - What file(s) where modified & their location
    - What configuration(s) were set
    - How to restart the service after a configuration change
    - Resources used (websites)
  - **_Webserver 1 & 2 configuration documentation requirements_**
    - What software / service needed to be installed
    - What file(s) where modified & their location
    - What configuration(s) were set (if any)
    - How to restart the service after a configuration change
    - Resources used (websites)
  - **_Screenshot(s) indicative that by connecting to the proxy, the proxy is connecting to the webservers to serve content_**
  - **_Link to your Elastic IP for your proxy_**


### Warnings:
    - You can have a maximum of **FIVE Elastic IP Addresses** 
    - To manage resources & keep costs down, you will need to delete your CloudFormation stack in between build & test

### Resources:
  - Note: feel free to share additional resources over in Discord.  I'll be updating this if I see you guys sharing something useful
  - https://www.haproxy.com/blog/the-four-essential-sections-of-an-haproxy-configuration/
  - https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-20-04 

## Extra credit (10%):
In your `AWS` folder in your repository, create a file called `cf-linter.md`.
- **_CloudFormation linter configuration documentation requirements_**
    - Describe your workflow - are you using VS Code, trying to run it in a terminal?  What environment am I expecting this to work in if I follow your guide
    - Describe installation and screenshot or highlight snippets (markdown) of how you are installing it
    - Tell me what the CF linter does and if it is useful.
- Notes: this package is brand new - I haven't played with it yet either.  Adopting / investigating new tools that could improve workflow is usually worthwhile so you have an informed opinion.  Sometimes things are a bust, but much like roasted brusselsprouts, you should try it before you bash it.
- https://dannys.cloud/level-up-cloudformation-with-vs-code
- https://marketplace.visualstudio.com/items?itemName=kddejong.vscode-cfn-lint
- https://github.com/aws-cloudformation/aws-cfn-lint-visual-studio-code 
- https://github.com/aws-cloudformation/cfn-python-lint

## Submission

In your GitHub repository, select the green `Code` button then select `Download ZIP`. Upload this zip file to Pilot.

In the `Comment` area in the Pilot Dropbox, copy URL / link to the repository corresponding to the project you are submitting.