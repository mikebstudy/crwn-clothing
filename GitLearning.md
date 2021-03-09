# GitLearning

### Intention

- Intend to learn git commands and cultivate experience using them for the following
    + Initial project setup and integration with github
    + Learn how to work with branches as snapshots at a certain point of time
    + Learn how to efficiently read and write git comments
        * In the past, I've noticed it is difficult to overcome git comment errors so I've started the process of not recording git detail in comments, just the one liners. 
        * [ ] At some point, I'd like to experiment with how to extract git comments and format them in a manner similiar to the README.md for convience and correction.
    + Learn how to work with a subproject version of the main project to be able to extract out certain pieces for other use elsewhere
+ Also wound up learning some about SSH to eliminate always typing in user id and pasword when interacting with Github
- Dropped A02.Git branch because it did not work out as a worthwhile branch
    + Did not realize it could not be updated on its own, but merging would force unintended updates of the main from other older things
    + So it was not a viable approach
    + A little later, conceived the idea of making main.<SubProject> branches for keeping subprojects independent

## Common commands and situations

### Setup for github

- `git remote -v`
    + will show the names (origin) and urls (..crwn-clothing-me1.git)
- `git remote add origin git@github.com:mikebstudy/crwn-clothing-me1.git`
    + if already exists, and is wrong then
        + git remote remove origin (to get rid of an origin and url)
- `git push origin main`

### SSH commands for github access - needed once per Bash session 

- `eval $(ssh-agent -s)`
- `ssh-add ~/.ssh/id_rsa_mikebstudy`
- `ssh -T git@github.com`

```
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_rsa_mikebstudy
ssh -T git@github.com
```

### Create new working branch for a lesson snapshot

New branch for a Lecture XX given a BriefNname - only done once so that each branch is a snapshot of the work/state of the repo

- `git checkout -b L0XX-BriefName` (it takes the current setting of the * as the starting point - ie the branch comes of the current node known as *)
- [ ] Does it work? - `git checkout -b L0XX-BriefName main` (may be needed to cause L0XX-name to start as though it was main or could be safe guard to insure starting point if from main and not somewhere else accidently)
- (Do the changes)
- (Make sure Readme and notes are all updated)
- (Readme should be updated with branch name and commit note)
- (Then do the git status, add, commit sequence to finalize)
- `git push origin L0XX-name` to push the branch to Github

Merge branch back into main and commit to Github

- `git checkout main` (goes back to main)
- `git merge --no-ff L0XX-BriefName` (does merge into main that was just checked out)
    + [ ] Learn when to use --ff (default) and --no-ff
- `git push origin main` to push the merged main to Github

### Create snapshot branch of main when work accidentally not started on a branch

- `git branch main`
- (Readme should be updated with branch name and commit note)
- (Add (Snapshot) in README after snapshot branch name)
- (Then do the git status, add, commit sequence to finalize main, but preface with 'Add BranchName(Snapshot): Regular commit note.)
- `git push origin main` to push the merged main to Github
- `git checkout -b L0XX-BriefName`
- `git push origin L0XX-name`

### Branch renaming

- When in (checked out) the branch: `git branch -m <new-branch-name>`
- When not in the branch: `git branch -m <branch-name> <new-branch-name>`
- To sync the remote to the new names, you have to push the `new-branch-name` and delete the `branch-name` **NOT TESTED YET**
    + `git push origin -u <new-branch-name>` (u resets the upstream branch)
    + `git push origin -d <branch-name>` (or -delete)

### Branch deleting

- Delete branch locally (cannot be on branch): git branch -d localBranchName
- Delete branch locally, if not merged or pushed (forces delete) (cannot be on branch): git branch -D localBranchName
- Delete branch remotely: git push origin --delete remoteBranchName

### Interrupting current work to work in another branch 

- Assume working in main
- git stash push (puts all files into a stash area and clears the branch)
- checkout/edit/commit other branch and commit (such as main.Setup for install of new stuff)
- git checkout main (ie beck to branch originally being worked in)
- (git merge --no-ff OtherBranch)
- git push origin main
- git push origin OtherBranch (not sure if this push sequence is best practice)
- git stash pop (puts all files back into branch from stash area and clears the stash of the entry)
- Resume work in main

## Research

### How is the branch node point determined?

- https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell
    + The branch is a pointer to the same commit you're currently on
    + See Creating a New Branch

### Viewing long log files

- PageUp, PageDown, ArrowUp, ArrowDown
- q to exit

### git difftool

DO NOT USE - could not find a way to exit screen
Instead use vscode diff function

### git rm

- removes files
    + but so far do not see a way to remove a file from a branch and still leave it in the system
        * this is because git rm removes and deletes the file out of the working directory on the next commit
            - so it would be a distructive test to try removing in one place in a branch and only have it actually removed from the whole system, because it does a remove from the working directory
            - it might be worth a try to see if it just drops it in one branch but leaves it elsewhere
                + the way git works seems that is should actually work because of its snapshot system
                + IT DID WORK

### Changing a comment or the file set that was committed

- if a commit has just been done, the comment and files can be changed
    + use git commit --amend
    + warning. be very careful. not known what happens if intervening things are done

### HEAD notes

- pointer to the current branch node that is the object of current staging and committing

### use --name-only

- used to print out list of changed files within a commit when using git log

