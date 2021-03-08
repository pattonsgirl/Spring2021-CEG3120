# Project 4

## Objectives:

- Explore distributed architecture via HAProxy

## 1. Load balancer with HAProxy

- Stand up proxy server (HAProxy)
- Stand up two apache or nginx servers
- Place a different `index.html` page on each server
  - You can use mine in the Project folder
- Create a private / public key
  - put public key on each server (**don't override the AWS key**)
  - put private key on the proxy
    - Hint: `sftp` instead of `ssh` and get the private key
- Security groups should be changed to the following rules:
  - Port 80 traffic from external
  - Port 22 traffic from external
  - Port 80 traffic in private subnet
  - Port 22 traffic in private subnet
- ~~The final product should NOT have elastic IPs for the webservers. The webservers will only use their private IPs~~

### Deliverables:

- CloudFormation template with everything **you** can automate
  - Note: this means best effort will be counted
  - Recommendation - build out what you can, get in the system, play with configuration. Once you know what goes where and have configuration files, then you can move forward with automation
- Documentation of what needed to be configured outside of the template, and what you did to make it happen.
  - ~~Hint: Snippets below show areas that need to be commented out / removed appropriately so that a public IP address does not associate with an instance:~~

```
#Ubuntu2IPAddress:
  #  Type: 'AWS::EC2::EIP'
  #  DependsOn: AttachGateway
  #  Properties:
  #    Domain: vpc
  #    InstanceId: !Ref Ubuntu2Instance
...
#AssociatePublicIpAddress: 'true'
DeviceIndex: '0'
#DeleteOnTermination: 'true'
```

**Resources**

- [HAProxy Load Balancer Ubuntu](https://upcloud.com/community/tutorials/haproxy-load-balancer-ubuntu/)
- [HAProxy & Load Balancing Concepts](https://www.digitalocean.com/community/tutorials/an-introduction-to-haproxy-and-load-balancing-concepts)
- [Configuring HAProxy to Set Up HTTP Load Balancing (Layer 4)](https://www.digitalocean.com/community/tutorials/how-to-use-haproxy-to-set-up-http-load-balancing-on-an-ubuntu-vps)
- [Configuring HAProxy for Layer 7 Load Balancing](https://www.digitalocean.com/community/tutorials/how-to-use-haproxy-as-a-layer-7-load-balancer-for-wordpress-and-nginx-on-ubuntu-14-04)

### Deliverables:

- `README-Milestone3.md` that describes your setup and has screenshots of your working implementation
- script(s), including hook(s) placed in your `scripts` directory

**Gotchas to Watch**

- May need to add private key to `.ssh/config` to use `git` with `ssh`
- For the webservers, make sure your user is the owner of `/var/www/html`. By default `root` is the owner.

**Resources**

- [Simple automated GIT Deployment using GIT Hooks](https://gist.github.com/noelboss/3fe13927025b89757f8fb12e9066f2fa)
- [How To Use Git Hooks To Automate Development and Deployment Tasks](https://www.digitalocean.com/community/tutorials/how-to-use-git-hooks-to-automate-development-and-deployment-tasks)
- [Customizing Git Hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)
- [Git - Working with Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
- [Git & Private Keys](https://superuser.com/questions/232373/how-to-tell-git-which-private-key-to-use)
- [Interesting Read - Hosting site from file server](https://www.digitalocean.com/community/tutorials/how-to-use-haproxy-as-a-layer-4-load-balancer-for-wordpress-application-servers-on-ubuntu-14-04)

**Samples**

- [scp](https://en.wikipedia.org/wiki/Secure_copy_protocol): `scp -i demo-key.pem test.txt ubuntu@54.227.255.221:/home/ubuntu/test.txt`
