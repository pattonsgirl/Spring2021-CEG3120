# Quiz 2

1. If given your API key for your Discord bot, I have the same permissions to access your Discord server / guild as you do.

- True.  API keys give me user authentication free access to the service associated with the key

2. Public keys go in what file of the system I am connecting to?

- `~/.ssh/authorized_keys`

3. At the moment, the Discord Bot only runs while there is a terminal session open with the process running.  What is a solution to this problem?

- `screen`
- `background jobs`
- What we are doing now: running python bot on a cloud service.
    - Next evolutions: investigate containers or other detached methods
        - pm2 works with node.js applications.  We have a python application.  Do you rewrite to go with a different platform?  Cobble together a solution to force it to work with node.js via proxy?

4. The ______ command can be used to get the status of a service, as well as start, stop, or restart it.

- `systemctl`

5. Write command(s) that will create and switch to a branch called `bot-patch`

- `git checkout -b bot-patch`