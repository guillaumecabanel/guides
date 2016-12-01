# Using git for collaboration

## Start a new branch
```
git pull origin master
git checkout -b NEW_BRANCH_NAME
```


## Push a branch on github
```
git add .
git commit -m "MESSAGE"
git checkout master
git pull origin master
git checkout BRANCH_NAME
git merge master
git push origin BRANCH_NAME
```
In case of conflict use `git status` to see conlicting files.

## Update master while still working on a branch
```
git add .
git commit -m ‘’
git status
git checkout master (or gcm)
git pull origin master
git checkout branch_name
git merge master
```

In case of conflict use `git status` to see conlicting files.

## Warning

Always check that your *status* is **clean** before changing branch.
