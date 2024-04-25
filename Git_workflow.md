One of my frustrations about tutorials for Git (and previously for Subversion) is that it is rare to find complete workflow examples that demonstrate how to use the tool on a daily basis. So here is how I use Git (and Github) every day.

These steps assume you want to mostly type in Git commands. There is also a Git GUI, and Git options built in to development environments like Jupterlab and MS VScode.  

## To start a new project
I navigate my browser to my home on Github, click on the "Repositories" tab, and click on the "New" button to create a project in my cloud account. I and tick the box that says Add `README.md` file.
I put a few notes in the README file about the project and save it. Now I have a repo with one file.  

Then click on the Clone or download button. (If you don't have SSH keys set up with GitHub, choose "Use HTTPS"). Then I click on the little clipboard icon to save the repo URL to my clipboard.

Now I fire up my local Git Bash desktop app. In that window:
```
cd <to the parent folder that will hold the project folder>
git clone <paste the URL>
```
Now I can move into that folder and start working
```
cd <down one level to the project folder>
```
The first thing I do is copy in my `disclaimer.md` and `license.md` files from somewhere else. You can use the ones in this repo. Then I `add` them, so they will be tracked by Git.  
```
git add *.md
```  
Then I usually start a Jupyter notebook and do some work. Then I add the notebook to be tracked by git.  
```
git add <name of notebook>
```  
When I am done working for a bit, I first "stage" and "commit" the changes, along with a short note, like:  
```
git commit -a -m "completed notebook demoing "
```  
The `-a` means all changed, tracked files will be staged and committed, and the `-m` refers to a "memo" or note regarding the commit. That updates the *local* version of the repo. To update the cloud version:  
```
git push
```


## If I am working on an existing project:
```
cd project_dir
git pull
```
That will ensure I get changes I may have saved from another computer, like when I work at home. Then I work, making changes to code. If I add files I want to track:

```git add file_name```

When I am done for this session...or always at end of day, I use the command that stages and commits all pending changes, with a "memo":

```
git commit -a -m "fixed all bugs"
git push
```

Now I fire up my local Git Bash desktop app. In that window I

```
cd parent_of_new_repo_dir
git clone git@github.com:csherwood-usgs/Demo_repository.git
```

At this point, the only files in the repo will be the .git directory and the README.md. The README.md is just a text file in which you can use the Git markdown syntax to write intelligible notes about the repo. This is actually easiest to do on the GitHub page, where you can preview the results.

The first thing I do with a new repo is copy the LICENSE and DISCLAIMER .md files from another repo. I hope these are ok...I inherited them from the one and only project I had published. (Note...the disclaimer changes when a project is officially published by the USGS...this is the disclaimer for unpublished code). Then I add, commit, and push those files, and I now have a project I can work on.

You can grab the license and disclaimer from my repo at:

https://github.com/csherwood-usgs/Demo_repository

