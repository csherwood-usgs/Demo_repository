One of my frustrations about tutorials for Git (and previously for Subversion) is that it is rare to find complete workflow examples that demonstrate how to use the tool on a daily basis. So here is how I use Git (and Github) every day.

## If I am working on the master branch of an existing project:
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
## If I want to start a new project:

1) Navigate to my home on Github

2) Click on the Repositories tab

3) Click on the New button

4) Enter a Repository name in the box, put in a one-line description in the next box, check the Public button, and check Initialize this repository with a README.

5) Click on create repository.

In the next screen, I click on the Clone or download button. (If you don't have SSH keys set up with GitHub, choose "Use HTTPS"). Then I click on the little clipboard icon to save the repo URL to my clipboard.

Now I fire up my local Git Bash desktop app. In that window I

```
cd parent_of_new_repo_dir
git clone git@github.com:csherwood-usgs/Demo_repository.git
```

At this point, the only files in the repo will be the .git directory and the README.md. The README.md is just a text file in which you can use the Git markdown syntax to write intelligible notes about the repo. This is actually easiest to do on the GitHub page, where you can preview the results.

The first thing I do with a new repo is copy the LICENSE and DISCLAIMER .md files from another repo. I hope these are ok...I inherited them from the one and only project I had published. (Note...the disclaimer changes when a project is officially published by the USGS...this is the disclaimer for unpublished code). Then I add, commit, and push those files, and I now have a project I can work on.

You can grab the license and disclaimer from my repo at:

https://github.com/csherwood-usgs/Demo_repository

