
# GitBranching
SCM with github: a Git Branching Workflow Exercise

### Adding an existing project to GitHub using the command line
[github tutorial](https://help.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line)

### Clone Exisitng Repository
    git clone https://github.com/stellactyy/GitBranching.git

#### 1. Open Git Bash
- cd to the repository localtion
#### 2. Create a new branch named "dev"
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
    
#### 3. START development on a new "feautre/<my_feature_name>" branch [ALL DEVELOPERS]
- all features to branch off dev

this way u will surely branch from dev

    git checkout b feature1mgfeature dev

    echo 2 do featurework only in ur own featurebranch WORKFLOW.md
    echo 3 commit regularly WORKFLOW.md
    echo 4 when unittesting is done commitlpush final changes and initiate pullrequest to der WORKFLOW.md
    echo 5 after reviewer approved merge featurebranchinto der WORKFLOW.md
    echo 6 delete feature branch WORKFLOW.md
    git commit a m added feature workflow in new feature branch
    git push --set-upstream origin dev

#### 4. CREATE a new "rel-<verion_num>" branch
All releases also branch off **dev** but merge back into both **dev** and **master**

    git checkout -b rel-1.0 dev
    echo "7. only do bugfixes & documentation in rel branches" >> WORKFLOW.md
    echo "8. use tagsto demarcate rel versions in master branch" >> WORKFLOW.md
    git commit -a -m "added release workflow in new rel-1.0 branch"
    git push
    git checkout dev
    git merge --no-ff rel-1.0 (use no-ff to alwayss show seperate branches in git history)
    git checkout master
    git merge --no-ff rel-1.0
    git tag -a r1.0 -m "this is the 1st release with workflow documentation"
    git push --tags (check that you have a new "release" item on github)


#### 5. CREATE a new **hotfix-<minor_version_num>** branch one [DEVELOPER1] that fixes a bug for a feature being coded concurrently [anotherDEVELOPERI]
all hotfixes branch off masterandmerge back into both deer and master


    [DEVELOPER 1] 
    git checkout -b hotfix-1.0.1 master 
    echo "9 almostthe sameas a relbranch but works off prev release version" >> WORKFLOW.md 
    git commit -a -m "added release workflow in new hotfix-1.0.1 branch"
    git push
    git checkout der hotfix-1.0.1
    git merge --no-ff potentially some manual merging required)
    git checkout master
    git merge --no-ff hotfix-1.0.1
    git tag -a r1.0.1 -m "fixed app-breaking workflow bug in rel-1.0"
    git push --tags
    git pull orgin dev (or initiate pull request from github interface)
    git commit -a -m "added hotfix dev workflow with fixes"
    git push

    [DEVELOPER 2]
    gitcheckout b feature Ifinal touch der
    echo "10 other developers continue work off the dev branch" >> WORKFLOW.md
