---
layout: post
title:      "Notes on how to use Git"
date:       2019-04-16 19:21:27 +0000
permalink:  notes_on_how_to_use_git
---


* Create a new directory locally by typing `mkdir my-project` in the terminal
* Then move into the directory by typing `cd my-project` in the terminal
* Initialize the directory by typing `git init`. Only type `git init` within the directory you want `git` to track


* Check the status of the repository by typing `git status` to see what changes have been made
* Create a README file by typing `touch README.md` within the directory
* Get a list of all the files in the directory by typing `ls`


* Add files to the `git` repository by typing `git add <filename>` or add all the files by typing `git add .`
* Commit the changes by typing `git commit -m 'message about the commit'`. Make sure the commit message is informative and specific.


* Make a local copy of a repo from Github by typing `git clone <URL>`. Get the URL by going to the repository on Github and clicking the "Clone or download" green button. Use SSH as the URL type. 
* See the names of each remote repository available by typing `git remote`. The remote repo you just cloned from is called `origin`
* Duplicate a repo by typing `git fork`. You will have your own copy and update it as you please. 


* Connect the local repo to the Github repo by adding a new remote to a remote name `git remote add origin <URL>`
* Push the local, committed work to the remote repo by typing `git push -u origin master`. Here `origin` is the repo name and `master` is the branch we are pushing this to. The first time you push code up to the remote repo, use the `-u` flag but afterwards you only need to enter `git push`
