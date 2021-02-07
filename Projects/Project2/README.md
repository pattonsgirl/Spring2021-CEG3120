# Project 2

## Objectives

- Play with branching & ignoring files in a repo
- Practice good documentation for a growing infrastructure
- Explore Elastic Cloud Computing & Virtual Private Clouds in AWS
- Play with regulating ports and firewall traffic


## branch-ing out

Create a branch in your repository called `git-guide-update`

Update your git guide using your project feedback (if any) and add the following:

- branch
  - how to create a branch
  - how to switch to a branch
  - how to make changes in a branch (what happens, do you still need commits?)
  - how to merge a branch with main / master

Merge your `git-guide-update` back to the main branch of your repository.

Note: it is not required that GitHub knows about your local branch - the important part is that your changes made on your branch end up on your main branch.

## Is it secret? Is it safe?

In the main folder of your repository, create a `.gitignore` file.  In this file, specify that you want `git` to ignore the file (use its full path) where you stored your key (likely in a `.env` file).

Update your `git-guide.md` to include how to use a `.gitignore` file.  If you already added your key (as in you can see it on GitHub) try to get rid of it.  Write the commands you've tried and their effect in your `git-guide.md` file.

## AWS Play Time

- Create a VPC on AWS.
- Create an 2 EC2 instances.  Utilize an Linux AMI, use only free tier resources.
- Attach an IP address to each.
- Utilize Security Groups to lock down inbound cloud traffic
    - Allow all traffic on all ports within the VPC subnet (likely 10.0.0.0/16)
    - Allow all traffic on ports 80 AND port 443 from the world
    - All SSH traffic only from your home network
      - Note: if you are connecting from multple locations, you can have a redundant rule to allow SSH from world or from a few other locations.

### AWS Educate Quick Link:

- [Sign in to AWS educate](https://www.awseducate.com/signin/SiteLogin)

### Deliverable:

The deliverable for this portion of the project is good documentation.  In the main folder of your repository, create a folder called `AWS`.  In that folder, create a file called `manual-mode.md`.  In this file, you will be documenting your progress with the above requirements.  Include a screenshot for each task and a description of how you did it.  As you go through, you may not get it perfect the first time.  Circle back to your documentation with notes about what had to be changed.

## Submission

In your GitHub repository, select the green `Code` button then select `Download ZIP`. Upload this zip file to Pilot.

In the `Comment` area in the Pilot Dropbox, copy URL / link to the repository corresponding to the project you are submitting.