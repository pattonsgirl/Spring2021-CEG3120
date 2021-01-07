# Project 5

## Objectives:

- Play with continuous deployment at a manual level

## 2. Implement Continuous Deployment (CD)

For this part, your goal is to have a main site and update all (in this case, 2) webservers at once. You may use a simple template, such as `index-main.html` that is in the project folder, or something complex, such as a personal site or site created in another class. Just make sure you are familar enough that you can make simple changes to the site to test your hooks.

- You will be using the `post-receive` hook to update the website folder once a change is made (`push` received) on the server side
- To deploy to multiple servers, you can choose a multitude of methods.
  - have `post-receive` hook on both webservers, then either:
    - add other server as a `remote` branch, `push` to it from development machine
    - create a special `push` alias, such as `push-sites` that pushes to both servers
  - use a file transfer command inside the `post-receive` script, such as `scp` or `rsync` to push files out to other server
  - something else I'm not thinking of but works?
    - Note: must use hooks to qualify as a valid solution
