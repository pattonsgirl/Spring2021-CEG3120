# Quiz 3

1. ____ templates are used on AWS to deploy stacks of resources.
    - CloudFormation

2. Identify and describe a load balancing allocation strategy.
    - round robin
    - least connections
    - weighted round robin
    - least response

3. I want to create a hook in git that will triggers when an update (push) is received by the server.  Name the hook that would best fit the scenario:
    - `pre-receive`
    - `post-receive` was also accepted, but its action would not start until after the receive was done.
    - accepted `update`
    - `pre-push` accepted, BUT `pre-push` updates with remote, but does not yet update content.  We'll chalk it up to a wording improvement needed


4. To restart a service (such as ssh, haproxy, or even apache2) I can use the ____ command.  This command can also be used in combination with start, stop, or status for the given service.
    - `systemctl`
    - Reboot will restart all services, but it's an all or nothing move.  `systemctl` will let you have more precise control over a single service.

5. Docker is the tool we are using to create containers.
    - True