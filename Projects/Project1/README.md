# Project 1

### Objectives:

- Get back into terminals and get comfortable with your environment
- Get more familar with git
- Create a replica GitHub server
- Create a Discord bot using Discord API calls in Python

## Setup your Workspace:

[AWS Setup Guide & GitHub Setup](../../AWS-Setup-Guide.md)

- Follow the guide to create a Linux system in AWS.
- Create a GitHub account
- Click the link in Pilot to create your GitHub repo for this course.
  - Recommended to bookmark the URL
  - `https://github.com/WSU-kduncan/ceg3120-YOURGITHUBUSERNAME`

## Git guide:

In the main folder of your repository, create a file called `git-guide.md` For each git command listed below, describe how to use it and what the command does. In addition, link to one cheat sheet for git commands and one reference guide, such as Pro Git.

- clone
- init
  - Flag to create a `bare` repository and definition of a `bare` repository
- add
- commit
- push
- pull

Use markdown to properly format your documentation by highlighting terminal text in a manner similar to:  
`git add`  
\`git add\`

## Create a Discord Bot using discord.py

1. Create a folder in your repository called `Discord-Bot`
2. Create a `README.md` file in this folder.
3. [Follow this guide](https://realpython.com/how-to-make-a-discord-bot-python/) to create a Discord bot in a Discord server you control.

- The code for the bot can run either from your personal machine OR run it on the Linux AWS system.
- I created a fresh Discord server to play around in. You are welcome to do this in any Discord server you have admin privledges or create your own (it's free)
- Put your `python` code in the `Discord-Bot` folder

4. Modify the bot code to do either of the following:

- outputs quotes based on a command of your choice
  - note that this _must_ be a different command and set of quotes from the demo
- outputs pictures based on a command of your choice
  - see `!corgme` in the Department server under Discussion. Please spam #cute-pets only

5. Update the `README.md` with documentation. Use each bulleted item as a header (see [markdown-demo](../../markdown-demo.md)):

- Description
  - What the code does
  - What commands the bot can use, and what they do.
- How to use an API key
  - You may assume the user has created a Discord API key; you do not need to details how to do this to the user
  - Where does the key need to be located? Is this an environment variable? How did it get "loaded" into the system?
- Dependencies
  - Is `python` required? What version? How do you install `discord.py`?

## Create a git "server"

Use your AWS environment to create a git server. You are going to build it similar to how GitHub hosts repositories. The end goal is be able to use a clone command via SSH authentication to clone a repository.

```
$ git clone git@Linux_AWS_IP:username/projectname
```

Guided questions:

1. What user are you authenticating as? Peek at the `@` symbol
2. `username/projectname` is a folder path. Where does it exist?
3. Investigate `git init --bare`
4. If you are authenticating using a specific user, where does the public key need to go for SSH authentication?

Deliverables:

In the main folder of your repository, create a folder called `servers`. In the folder, create a file called `git-server.md`. Use each bulleted item as a header (see [markdown-demo](../../markdown-demo.md)):

- How to:
  - Details on how you setup the remote computer to host a git repository
- Cloning:
  - What does the server need from another computer for the `clone` to work? (think about SSH)
  - Take a screenshot of a working clone as proof of your correct configuration.

## Submission

In your GitHub repository, select the green `Code` button then select `Download ZIP`. Upload this zip file to Pilot.

In the `Comment` area in the Pilot Dropbox, copy URL / link to the repository corresponding to the project your are submitting.
