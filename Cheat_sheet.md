## Notes on Git and Github commands

### Determine the origin URL of a local .git repo:
```
git config --get remote.origin.url
```  
---
### Switch a repo from HTTPS to SSH authentification:
```
git remote set-url origin git@github.com:csherwood-usgs/jsed.git
```
where the last argument is the URL, which you can grab from the "Clone or download" box in the repo.  
---
### Good tutorial on GitHub workflow

https://github.com/readme/guides/configure-git-environment
