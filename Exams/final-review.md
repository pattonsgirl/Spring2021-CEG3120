# Final Review for CEG 3120
## Spring 2021

## Da Rules

Midterm: Monday, 4/26

- Available 8:00 AM to 11:59 PM
- 1 attempt, 2 hours once started
- Open note, open terminal

## Topic List

### Load balancing & webservers
- load balancer
    - define backend cluster of resources that host content
    - can define if server hold unique content (a set that has shop.site.com vs blog.site.com) or if all servers have same content
    - the public ip (ip people connect to) is now the ip of the load balancer.  User does not need ips of webservers
    - load balancer maintains connection between client and backend server (persistance & connection maintainence)
    - handles fault tolerance is backend server(s) are down - can show error pages and / or take downed server out of connection queue
    - Allocation strategies
        - Round robin
        - Weight round robin
        - Least connections
        - Least response time
    - haproxy (high availability proxy) configurations:
        - global - haproxy permissions on system, default logs, system performance tuning
        - defaults - settings to apply to frontend and backend configurations
        - frontend - defines client connections and pairs with backend cluster - client to shop.site.com uses backend shops
        - backend - defines allocation strategy and ips (or names if internal DNS) of system group - shops might include serv3 and serv6
    - monitoring system health
        - haproxy has built in stats page
        - may want to investigate dashboard for flashier setups and to integrate other servers
- Webservers
    - HTTP - port 80
    - HTTPS - port 443
    - common server backends: apache2 & nginx

### git & GitHub
- hooks
    - exist in .git folder local to repo - they do not get pushed to GitHub
    - must be in hooks folder, must have exact name and be executable for hook to trigger
    - Client side hooks
        - pre-commit - must be successful / check before commit completes, trigger when commit is run
        - pre-push - triggers when push command is run, before communicating with GitHub
    - Server side hooks - note: can put on a server you host, but not on GitHub
        - pre-receive
            - client has pushed, runs when server is contacted to receive data
        - post-receive
            - client has pushed, runs once data has been received
            - was used in demo to deploy updates (put new content in folder) once developer (client) had pushed
- GitHub Actions
    - must exist in .github/workflows folder in your repo
    - Workflows define the following:
        - events - what triggers the workflow - triggers can be:
            - external events completing (CodeBuild return success)
            - GitHub events: push received, pull requests, release versions
        - runners - the virtual machine that runs the jobs in the workflow
            - pick from Ubuntu Linux, Windows, or Mac runners
        - jobs - collection of steps executed on runner
        - steps - GitHub actions or commands to be run
        - actions - specialty GitHub actions that do things, like checkout the project to the runner
- GitHub Secrets
    - encypted storage of protected information (API keys, IAM credentials, etc) - maps secret to variable name
    - can call on secret values with notation: ${{ secrets.SECRET_VARIABLE }}

### Containers
- Reason to use containers
    - bundle dependencies and project files into mobile form 
    - can now deploy to anything that can run a container (has docker installed)
    - can choose a base to build from that has most of what your project needs
- Docker
    - Dockerfiles & basic instructions
        - FROM
        - COPY
        - RUN
    - build: builds an image using the Dockerfile
        - creates an image (runnable version) based on your specifications
        - -t flag lets you add a tag; can do multiple tags, like a version number & latest
        - . tells docker build where to find the Dockerfile
    - run: specify the image
        - -d to run container in detached mode (can continue even if terminal connection is not maintained)
        - -p specificies a port bind from the container port running a service to the host port
- Container registeries
    - where you can `pull` and `push` images
    - can `push` images once new version is ready.  Makes rollbacks easier.
    - Docker Hub, Elastic Container Registry are examples of registries

### Continuous integration / Continuous deployment
- test before deployment
    - AWS CodeBuild, GitHub workflows
    - idea of creating units tests to verify all systems are good before making changes to production
- want to have trigger that kicks off version updates across servers with minimal manual interaction
- can manually create functionality (git hooks, scripts, etc)
- can use hosting company features to assist (GitHub Actions)

### Ignoring for exam topics but discussed:
- directory services
    - server or set of servers that hold directory info (users, groups, resources) that you can configure your system to connect to for authentication
    - solves problem of trying to create users on every system
- AWS IAM users / groups
    - AWS accounts, when created from scratch, are full access - you control billing, resource creation, whole shebang
    - for organizations, you don't want everyone with their own account, you want an organization account with other people having appropriate access
    - enter IAM users - create additional users and their access level for your overarching account.
- AWS Elastic Container Service
    - can run docker containers on AWS resources without manual interaction
    - could set workflow to deplow new image version to ECS when a new image has been built.

## Previous Topics: Familiarity Expected

### git 
- clone
    - git clone followed a url / ssh link a copy of a workspace (whatever is on the remote repository) and a .git folder that hold configurations (include connection back to remote repo)
- init
    - initializes a new repo given a folder name (by default this is with a workspace and a .git folder for configuration)
    - `--bare` only contents of what is normally in a .git folder
- add / rm
    - how we add a file or set of files for tracking
    - rm how we remove a file from tracking
- status
    - tell you where your repo stands
- commit
    - creating a snapshot of changes with a corresponding message
- push
    - I have content - commits - in my local repository that I want to push to the remote repository (GitHub)
- pull
    - there is content on GitHub (the remote repo) that is not in local repo
- merge
    - merge conflicts (conflict area in the file(s) will be annotated with <<<<<<<>>>>>>>)
- branch
    - why branches?
    - create a branch
        - git checkout -b new_branch_name
        - git branch new_branch_name
    - switch branches
        git checkout branch_to_switch_to
    - merge branches?
        - go back to branch we want content on, then do a merge of branch we want to pull from
- .gitignore
    - usually in main folder of repo
    - usua relative paths to what you want to ignore (not use for tracking)
- hooks
    - intro level: concept that the can tie scripts to certain git commands 
        - pre-commit ties to git commit locally
        - post-recieve ties to after push confirmed on remote

### authentication
- SSH keys
    - public keys & where they go
    - private keys & where they go
    - default files:
        - ~/.ssh/config
        - ~/.ssh/authorized_keys
- API keys
    - security concerns
    - what side creates the key (side you are connecting to / requesting info from)

### networking
- Public vs private IPs
    - NAT (or "Internet Gateway" per AWS) to bind to reach outside
- CIDR notation
    - 130.108.0.0/16 - subnetmask 255.255.0.0 - IP address range 130.108.0.0 - 130.108.255.255
    - 67.123.43.23/32 - subnetmask 255.255.255.255 - IP address 67.123.43.23
- Firewalls
    - by ip address and / or by port
- Ports
    - SSH 22
    - HTTP 80
    - HTTPS 443
- proxies
     - load balancing
- caching servers

### Command line know how:
- install package with pip
- running a python script
- file / folder permissions
    - user / group / other
        - chmod, chown, chgrp
    - creating users
        - adduser
- process control (ps -aux, top/ htop, pstree, kill, systemctl)
- process logs (systemctl for recent snippet, journalctl for history over time)
- detaching from the terminal
    - background jobs
    - screen

### AWS
- Regions & computational resources
- AMIs
- VPC
    - VPC subnet
- Security groups
- EC2
- CloudFormation template
    - Infrastructure as Code