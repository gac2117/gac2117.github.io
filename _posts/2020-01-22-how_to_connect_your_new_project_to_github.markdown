---
layout: post
title:      "How to connect your new project to GitHub"
date:       2020-01-22 21:19:19 +0000
permalink:  how_to_connect_your_new_project_to_github
---


This blog post will cover how to create a new repository on GitHub and connect your new local project to it.
This post has been written with the assumptions that you already installed git locally, you have a GitHut account, and you are connected to it on your local machine.

### In your terminal, 
1. Create a new directory for your new project (ex. "*my-project*") by typing `mkdir my-project` 
2. Move into that directory: `cd my-project` 
3. Now in the "my-project" directory, create some files, like a README file: `touch README.md` 
4. Initialize the directory: `git init`
5. Stage all the files: `git add .`
6. Commit the files with a message "*initial commit*": `git commit -m ‘initial commit’`

### Log into your GitHub account and [create a new repository](https://github.com/new ) 
1. Create a repository name and description
2. Decide if you want the repo to be *public* or *private*. Most likely you would want it to be public so others can see your code.
3. Don’t check the "*Initialize this repository with a README*" option because we are importing an existing repo
4. Click on "*Create Repository*"

### Copy the two lines of code
In the section: *…or push an existing repo from the command line*:

`git remote add origin <URL>`

`git push -u origin master`

### Go back to your terminal
In the "*my-project*" directory, paste those two lines of code.

Now your local repo is connected to GitHub and the changes you make will show up in your GitHub repo.

### Moving forward, make sure to commit any changes frequently.
1. `git add <filename>` will stage just that file. Or use `git add .` to stage all the files you've changed
2. `git status` will check the status of the repo and show any files that are not yet staged
3. `git commit -m ‘commit message’` will commit the changes with a commit message
4. `git push` will push the changes to the repo 
