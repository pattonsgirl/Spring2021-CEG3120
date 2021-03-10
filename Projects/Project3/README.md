# Project 3

## Objectives

- Practice good documentation for a growing infrastructure
- Create a CloudFormation template for an infrastructure
- Explore distributed architecture via HAProxy

### AWS Educate Quick Link:

- [Sign in to AWS educate](https://www.awseducate.com/signin/SiteLogin)

## Load balancing with HAProxy

You are going to configure an environment per the following requirements.  Note that you can start by creating everything manually, but part of your deliverables will be a CloudFormation template that stands this layout up.

- Stand up proxy server (HAProxy)
- Stand up two apache or nginx servers
- Place a different `index.html` on the HTTP servers
  - You can use mine in the Project folder
- Configure the HAProxy server to balance requests between the two web servers
  - Use Layer 4 for this set up
- Security groups should be changed to the following rules:
  - Port 80 traffic from external
  - Port 22 traffic from external - you can make this just your IP address
  - Port 80 traffic in private subnet
  - Port 22 traffic in private subnet

### Deliverables

1. In your `AWS` folder in your repository, have your CloudFormation template that is used to create the infrastructure detailed above.
2. In your `AWS` folder in your repository, create a file called `proxy-config.md`.  In this file document how you got the proxy 

## Extra Credit: A sprinkle of automation



### Warnings:
    - You can have a maximum of **5 Elastic IP Addresses** 

## TODO List:

- [Simplified Example Config File](sample-config-file.yml)
- [Example Configuration File](https://github.com/mkijowski/aws-cf-templates/blob/master/course-templates/ceg3400.yml)
- Scope: "configurations" will include software that needs to be installed on the system. Do not deal with configuration files.
- Note: to keep costs down, you will need to delete your Cloud Stack in between build & test



Extra credit:
Play with AWS Cloud Formation linter
Notes: this package is brand new - I haven't played with it yet either.  Adopting / investigating new tools that can improve workflow is always worthwhile.  Sometimes things are a bust, but much like roasted brusselsprouts, you should try it before you bash it.
https://dannys.cloud/level-up-cloudformation-with-vs-code
https://marketplace.visualstudio.com/items?itemName=kddejong.vscode-cfn-lint
https://github.com/aws-cloudformation/aws-cfn-lint-visual-studio-code 
https://github.com/aws-cloudformation/cfn-python-lint
