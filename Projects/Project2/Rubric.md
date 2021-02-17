# Project 2 Rubric

 / 15

## branching and merging changes to git-guide.md - / 5
- branch created
- `git-guide.md` updated on branch with info about branching
    - how to create a branch
    - how to merge a branch
- branch merged with main, `git-guide.md` is updated on main via the merge

## .gitignore - / 3
- File exists in main folder of repo
- File specifies API key
- Documentation of `.gitignore` file in `git-guide.md`

## AWS manual resource creation - / 7
- `manual-mode.md` exists in `AWS` folder
- Screenshot & documentation of the following resources
    - Create a VPC on AWS.
    - Create 2 EC2 instances using free tier linux AMIs.
    - Attach an IP address to each.
    - Utilize Security Groups to lock down inbound cloud traffic
        - Allow all traffic on all ports within the VPC subnet (likely 10.0.0.0/16)
        - Allow all traffic on ports 80 AND port 443 from the world
        - All SSH traffic only from your home network