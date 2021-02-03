# Project 2

## Objectives

- Practice good documentation for a growing infrastructure
- Explore Elastic Cloud Computing & Virtual Private Clouds in AWS
- Play with regulating ports and firewall traffic

## branch-ing out

Create a branch for your project called `git-guide-update`

Update your git guide using your project feedback (if any) and add the following:

- branch
  - how to create a branch
  - how to switch to a branch
  - how to make changes in a branch (what happens, do you still need commits?)
  - how to merge a branch with main / master

Merge your `git-guide-update` back to the main branch of your repository.

Note: it is not required that GitHub knows about your local branch - the important part is that your changes made on your branch end up on your main branch.

## TODO List:

- Create a VPC on AWS.
- Create an OpenLDAP server
- Attach an IP address to each.
- Make networking decisions and open ports appropriately.
  - In VPC, utilize Security Groups to lock down cloud traffic
    - Edit inbound (ports for our services, traffic on 10.0.0.0/16)
    - Outbound does not need to be edited

### AWS Educate Quick Link:

- [Sign in to AWS educate](https://www.awseducate.com/signin/SiteLogin)

## Deliverables:

The primary deliverable for this project is a changelog that includes the components listed below. You may do this by using GitHub Projects in your class repository or by manually keeping track of changes. Since we will be building from this project, your log should include a date and/or time implemented. You may choose to break up the tasks into their own changelogs. I would get templating then check with me if you have concerns about your changelog.

I have no preference on if you manipulate your repository via the AWS instance that was created for us or use your repository locally.

### Changelog management includes:

- A record of changes made over time
- Justifications
- Resources used as a template for your installation / configuration
- Screenshot of the result

### Rubric:

### Template changelog:

Note: I tend to think of changelogs as old events sinking to the bottom - therefore most recent changes end up at the top.

# Changelog Project 2

## Server Configurations

### 10/24/2020 Installed git server

- Installed based on guide
- Create git user
- Password hint coursegit
- Setup ssh key on local system, uploaded public key to git user authorized_keys file
- Verified ssh key works by ssh'ing to system
- Put bare repo on remote, cloned local.
- Initialized repo on local, still needed to create bare on remote
  - Had to use `git push -u origin master`
  - TODO: Figure out bare, scp, and the key to happiness.

## Instances on AWS

### 10/25/2020 instance for OpenLDAP

- Created Ubuntu 20.x server, tied IP 34.226.227.216
- Install OpenLDAP [based on guide](find a guide)
  - Password hint classslapd
  - dc 3120-proj2.org

### 10/15/2020 trashed instance

- GitLab requires more resources (setup on t2.micro server). Tanked system during install.
- Create new instance, taking manual server approach
- Git server IP: 35.153.218.176

### 10/14/2020 created instances

- Created instance from Ubuntu AMI to manually install git server
- Created instance from Ubuntu AMI to create SLADP server  
  ![screenshot of instances](../../proj2pics/instances.png)

## Configure VPC in AWS

### 10/25/2020 security group update

- added port 339 inbound access to security group

### 10/22/2020 restricted inbound traffic in security group

- allows only from home network

### 10/15/2020 security group update

- Based on security rules from templated AWS system.
- Added inbound rules for SSH (22) traffic
- Need ports x open for SLADP and x open for GitLab.  
  [screenshot of security group rules]

### 10/14/2020 creation

- Created VPC via wizard with default network rules
- VPC id: vpc-07021ac52230b011f
  [screenshot of VPC]
