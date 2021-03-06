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

## Rename a branch
On the branch you want to rename :
```
git branch -m BRANCH_NAME
```

## Push a branch on github
```
git add .
git commit -m "MESSAGE"
git push origin BRANCH_NAME
```
In case of conflict on github, talk to your team to solve it.

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

## Import the branch of a team member
On master:
```
git branch BRANCH_NAME
git checkout BRANCH_NAME
git pull origin BANCH_NAME
```
