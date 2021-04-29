## Written answer: (8 pts)

1. List two load balancing allocation strategies and describe how they work.
  - round robin - given a list of systems, each system is given the next connection request in turn
  - weighted round robin - manually factor in machine capabilities, so if a machine has better specs for handling more connections, it can be given more
  - least connections - if a system has fewer connections, distribute next connections to it
  - least response time - allocate based on most repsonsive machines
  - more strategies described here: https://kemptechnologies.com/load-balancer/load-balancing-algorithms-techniques/

2. In a haproxy configuration file, what do sections labeled with "backend" define?
  - The backend sections define the group of servers that hold content defined by the frontend

3. What is the purpose of GitHub secrets (or any secret manager)?  Describe in terms of protection and usage of the stored information.
  - The secret managers store information in an encrypted format.  Using GitHub secrets as an example, I define a secret value and variable name in my repository.  Other scripts, like workflows, can then reference the stored secret instead of needing to reference a local file or have the information otherwise stored publicly.

4. What is the benefit of having workflows in your organization for continuous deployment?
  - Favorite student answer: Now-a-days time is of the essence. And with us building machines that can do a lot of the automated, time consuming work for us, faster than most humans, automation of a continuously deployed workflow is extremely beneficial. It also instills confidence in the members of the organization, as the system can utilize these deployed workflow actions to error test and ship updates out to your teams and clientele with little human involvement.

5. Explain the security groups rules given the following definition from a CloudFormation template and determine if the rules apply to inbound or outbound traffic:
```
LinuxSecurityGroup:
    Type: 'AWS::EC2::SecurityGroup'
    Properties:
      VpcId: !Ref VPC
      GroupDescription: Exam rules.
      SecurityGroupIngress:
        - IpProtocol: tcp
          FromPort: '22'
          ToPort: '22'
          CidrIp: 23.24.12.45/32
        - IpProtocol: tcp
          FromPort: '80'
          ToPort: '80'
          CidrIp: 0.0.0.0/0
        - IpProtocol: tcp
          FromPort: '1'
          ToPort: '445'
          CidrIp: 10.0.0.0/16
```
  - the rules are for inbound traffic (SecurityGroup**Ingress**)
  - Port 22 is open to IP 23.24.12.45
  - Port 80 is open to the world (0.0.0.0/0)
  - Ports 1 through 445 are open to subnet 10.0.0.0/16

## Written commands / code: (out of 10)

1. Write a command that will restart the haproxy service (no reboots).
  - `sudo systemctl restart haproxy`

2. What event will trigger the following workflow?
```
name: Test Code
on: [push]
jobs:
  execute:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: apt install python3
      - run: python my-code.py
```
  - a push (on any branch) to the repository

3. What type of runner does the job execute on for the following workflow?
```
name: Test Code
on: [push]
jobs:
  execute:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: apt install python3
      - run: python my-code.py
```
  - ubuntu-latest - latest version of Ubuntu Linux available to the runners (virtual machines that will execute the job specified)

4. What does the job do in the following workflow?
```
name: Test Code
on: [push]
jobs:
  execute:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: apt install python3
      - run: python my-code.py
```
  - checkout the contents of my repo to the runner
  - installs python3
  - executes my-code.py
    

5. Describe what is happening given the following Dockerfile contents
```
FROM haproxy:2.3
RUN apt update
RUN apt install python3
COPY ./my-proxy.cfg /usr/local/etc/haproxy/haproxy.cfg
```
  - gets base image haproxy:2.3
  - runs apt updates in container
  - installs python3 in container
  - copies my-proxy.cfg to specific spot in container

## Fill in the blank

1. In a default installation of Apache HTTP server, content is served over port ____ by default.
  - 80

2. GitHub Action workflows must be in the ____/____ folder of a repository in order for GitHub to detect them.
  - .github/workflows

3. ____ is one of many container repositories where container images can be pushed (to store them in the repository) and pulled (in order to deploy / download a version from the repository)
  - ECR / Elastic Container Repository
  - Docker Hub / Docker (online assumed)

## True / False

1. The command: "docker push httpd:2.4" will download the httpd:2.4 image from Docker Hub.
  - False.  Replace "push" with "pull"

2. A container image can run on any computer that has docker installed (assuming hardware requirements are met).
  - True

3. The command "docker run -p 5005:443 myapp:latest" will bind to the container's port 5005 and open port 443 on my local machine.
  - False, definitions flipped.  It will connect to port 443 in the container and bind to the local port 5005

4. A hook named "pre-push", assuming it exists in .git/hooks in the repository, will trigger when "git push" is run in the repository.
  - True