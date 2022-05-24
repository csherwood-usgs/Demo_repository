## Conda tips (how to install git, conda, git and a basic environment...Windows)

## Get an account at Github
USGS convention is to establish your user profile as `username-usgs`  
where "username" is your email handle (e.g., `username@usgs.gov`)  

## Install git for Windows
https://git-scm.com/download/win  
Follow the instructions here to set up git:  
https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup  
Your settings will be stored in `\Users\username\.git`.  
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
## Workflow
#### Make a new repo
Whenever I start a new project, I make a repo in github.  
On my home github page, I go to `repositories` and select `new`.  
After naming it (lets call it `mynewrepo`, put a short description in the bubble and check `Add a README file`, then `Create repository`. Then edit the README.md file, adding some notes and maybe indicating where the file will reside on your computer(s).  
#### Clone the repo to your local computer
Click the green `Code` button and copy the URL for the repo. The URL will be something like `https://github.com/csherwood-usgs/mynewrepo.git`. Note that you can choose how to tranfer code to/from your repo. If you have not set up SSH keys (a topic for another day), then you will choose `https` and be required to submit a password when uploading.  
On your local computer, change to the folder that contains your coding projects (in subfolders), and type:  
`git clone [paste in URL]`  

#### Add some boilerplate to the repo  
I always put a DSCLAIMER.md and LICENCE.md file in my repo.  `cd` to the repo, and grab these files from this repo.  
#### Add new files to track in the repo  
Any time you add files to the project folder and want to track them in git, you have to add them to the repo.  
`git add *.md`

Same thing if you created a Jupyter notebook:  
`git add mynewnotebook.ipynb`

### Commit your changes and push back to the cloud
`git commit -a -m "some userful comment"`  
where `-a` commits all tracked files that have changed,   
and `-m "text"` adds a memo to comment on the changes. Then  
`git push`  
will copy the changes to github.
###
