# GitBranching
A Git Branching Workflow Exercise

# SCM with github: a Git Branching Workflow Exercise
## Clone Exisitng Repository
    git clone https://github.com/stellactyy/GitBranching.git

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
    
## 3. START development on a new "feautre/<my_feature_name>" branch [ALL DEVELOPERS]
- all features to branch off dev

this way u will surely branch from dev
    git checkout b feature1mgfeature dev
   
    echo 2 do featurework only in ur own featurebranch WORKFLOW.md
    echo 3 commit regularly WORKFLOW.md
    echo 4 when unittesting is done commitlpush final changes and initiate pullrequest to der WORKFLOW.md
    echo 5 after reviewer approved merge featurebranchinto der WORKFLOW.md
    echo 6 delete feature branch WORKFLOW.md
    git commit a m added feature workflow in new feature branch
    git push
