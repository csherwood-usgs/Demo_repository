## Check upstream repos
```git remote -v```

## Sync a local repo that has been forked with the original

https://help.github.com/articles/fork-a-repo/

```git fetch upstream```

### Large file storage (>50 MB)

https://git-lfs.github.com/

```
git lfs install
git lfs track bigfile.tif
git add .git attributes
git add bigfile.tif
git commit -a -m "using lfs for bigfile.tif"
git push
```
