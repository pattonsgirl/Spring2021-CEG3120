# Midterm Review for CEG 3120
## Spring 2021

## Da Rules

Midterm: Friday, 2/26

- Available 8:00 AM to 11:59 PM
- 1 attempt, 2 hours once started
- Open note, open terminal
- No class - only exam

## Topic List

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