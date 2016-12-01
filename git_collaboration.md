# Using git collaboration for Rails app

:warning: Always check that your *status* is **clean** before changing branch.

## Get last master from github
On master:
```
git pull origin master
bundle install
rails db:migrate
```

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
git commit -m "MESSAGE"
git checkout master
git pull origin master
git checkout BRANCH_NAME
git merge master
```

In case of conflict use `git status` to see conlicting files.

## Clean old branches
On master:
```
git pull origin master
git sweep
```
