## Conda tips (how to install git, conda, git and a basic environment...Windows)

## Get an account at Github
USGS convention is to establish your user profile as `username-usgs`  
where "username" is your email handle (e.g., `username@usgs.gov`)  

## Install git for Windows
https://git-scm.com/download/win  
## Install either miniconda or anaconda  
Miniconda is lighter weight and does not provide the GUI Launcher, but works fine.  
I recommend the full Anaconda distribution for broader compatibility with others.  
https://docs.anaconda.com/anaconda/install/index.html  
## Install a conda environment
The big advantage of environments is that allows you to track and maintain the packages you need for your programs.  
A good start is the IOOS environment that provides many of the packages needed for earth sciences application.  
This doc provides good guidance for the conda installation and a good starter enviroment:  
https://ioos.github.io/ioos_code_lab/content/ioos_installation_conda.html  

## Adding to environments  
When your code requires a package that is not in your current enviroment, you may want to add to that environment.  
Try to do this using `conda install somepackage` or `mamba install somepackage`, and resist the temptation to do `pip install somepackage`. This will keep your environment more consistent.  

## Consider adding standard bash commands to your enviroment  

To install basic Linux commands in the anaconda window: `conda install m2-base` 
---
---
## Workflow
#### Make a new repo
Whenever I start a new project, I make a repo in github.  
On my home github page, I go to `repositories` and select `new`.  
After naming it, I put a short description in the bubble and check `Add a README file`, then `Create repository`. Then I edit the README.md file, adding some notes and often indicating where the file will reside on my computer(s).
