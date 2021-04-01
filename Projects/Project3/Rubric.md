# Project 3 Rubric

  / 10

## CloudFormation Template -  / 4
- `cf-template.yml` exists in `AWS` folder
- `cf-template` modified to perform the following:
    - 3 EIPs instead of 1
    - 3 EC2 instances instead of 1
      - Changes to the package list per what software needs to be installed where
    - Changes to Security Group rules

## HaProxy setup + webservers -  / 6
- `proxy-config.md` exists in `AWS` folder
- **_HAProxy configuration documentation requirements_** - / 2
    - What software / service needed to be installed
    - What file(s) where modified & their location
    - What configuration(s) were set
    - How to restart the service after a configuration change
- **_Webserver 1 & 2 configuration documentation requirements_** - / 2
    - What software / service needed to be installed
    - What file(s) where modified & their location
    - What configuration(s) were set (if any)
    - How to restart the service after a configuration change
- **_Screenshot(s) indicative that by connecting to the proxy, the proxy is connecting to the webservers to serve content_** - / 1
- **_Link to your Elastic IP for your proxy_** - / 1

## Extra credit: / 1
- `cf-linter.md` exists in `AWS` folder
- **_CloudFormation linter configuration documentation requirements_**
    - Describe your workflow 
    - Describe installation and screenshot or highlight snippets (markdown) of how you are installing it
    - Tell me what the CF linter does and if it is useful.