# Crown Clothing E-Commerce Project Site

Project site for Complete React Developer Course

### Setup/Build operations throughout course compiled into one spot

A01.Setup: Run npx create-react-app, then start Readme

- Add repo to GitHub
- Create folder for project ie `crwn-clothing`
- cd into folder
- `git clone <SSH URL> .` (causes clone into current folder)
    + adds git with single `Initial commit` 
        * Apparently using author from github site and name and email
- `npx create-react-app .` (to create in current folder)
    + when done in this sequence, there is no extra git commit created by npx

A01.Setup: Add sass

- `yarn add node-sass`

### Common git commands

A02.Git: Add git commands to create and use branches as snapshots

Common git commands

Setup for github

- `git remote -v`
    + will show the names (origin) and urls (..crwn-clothing-me1.git)
- `git remote add origin git@github.com:mikebstudy/crwn-clothing-me1.git`
    + if already exists, and is wrong then
        + git remote remove origin (to get rid of an origin and url)
- `git push origin main`

New branch for a lesson xx given a brief name - only done once so that each branch is a snapshot of the work/state of the repo

- `git checkout -b L0XX-name` (i think it takes the current setting of the * as the starting point)
- ? `git checkout -b L0XX-name main` (may be needed to cause L0XX-name to start as though it was main or could be safe guard to insure starting point if from main and not somewhere else accidently)
- (Do the changes)
- (Make sure Readme and notes are all updated)
- (Readme should be updated with branch name and commit note)
- (Then do the git status, add, commit sequence to finalize)
- `git push origin L0XX-name` to push the branch to Github

Merge branch backinto main and commit to Github

- `git checkout main` (goes back to main)
- `git merge --no-ff L0XX-name` (does merge into main that was just checked out)
- `git push origin main` to push the merged main to Github


