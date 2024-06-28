One of my frustrations about tutorials for Git (and previously for Subversion) is that it is rare to find complete workflow examples that demonstrate how to use the tool on a daily basis. So here is how I use Git (and Github) every day.

These steps assume you want to mostly type in Git commands. There is also a Git GUI, and Git options built in to development environments like Jupterlab and MS VScode.  

## To start a new project:
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
This is an assumed shortcut for
```
git push origin main
```
where `origin` refers to the target repo, and `main` refers to the current branch you want to push.

## To continue working on an existing project:
On my local computer:
```
cd <project_dir>
git pull
```
That will ensure I get changes I may have saved from another computer, like when I work at home. Then I can work on code. If I add a file I want to track:
```
git add <file_name>
```
If I want to delete a file and no longer track it:
```
git rm <file_name>
```
When I am done for this session...or always at end of day, I use the command that stages and commits all pending changes (locally) with a "memo", and push those changes up to the cloud repo:
```
git commit -a -m "fixed all bugs"
git push
```
