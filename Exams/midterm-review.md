# Midterm Review for CEG 3120
## Spring 2021

Project 2 grades posted

## Da Rules

Midterm: Friday, 2/26

- Available 8:00 AM to 11:59 PM
- 1 attempt, 2 hours once started
- Open note, open terminal
- No class - only exam

## Topic List

### git 
- clone
- init
- add / rm
- commit
- push
- pull
- merge
- branch
    - create a branch
    - switch branches
- .gitignore
- hooks
    - intro level: concept that the can tie scripts to certain git commands 
        - pre-commit ties to git commit locally
        - post-recieve ties to after push confirmed on remote)

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
- Firewalls
- Ports
- proxies
- caching servers

### Command line know how:
- install package with pip
- running a python script
- file / folder permissions
    - user / group / other
    - creating users
- process control (ps -aux, top, pstree, kill, systemctl)
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
