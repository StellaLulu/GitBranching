# SCM with github: a Git Branching Workflow Exercise
## 1. Open Git Bash
- cd to the repository localtion
## 2. Create a new branch named "dev"
To check that you are in master branch

    git branch 

Create a new branch and switch to it in one step
    
    git checkout -b dev 



    echo "1. though shall always commit to dev before master" >> WORKFLOW.md
    git add .
    git commit -m "created WORKFLOW.md in new dev branch"
    git push

if there is an error message

fatal: The current branch dev has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin dev