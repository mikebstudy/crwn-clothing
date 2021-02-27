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

...A02.Git: Add SSH commands for github 

SSH commands for github access - needed once per Bash session 

- `eval $(ssh-agent -s)`
- `ssh-add ~/.ssh/id_rsa_mikebstudy`
- `ssh -T git@github.com`

...A02.Git(end)

New branch for a lesson xx given a brief name - only done once so that each branch is a snapshot of the work/state of the repo

- `git checkout -b L0XX-name` (i think it takes the current setting of the * as the starting point)
- ? `git checkout -b L0XX-name main` (may be needed to cause L0XX-name to start as though it was main or could be safe guard to insure starting point if from main and not somewhere else accidently)
- (Do the changes)
- (Make sure Readme and notes are all updated)
- (Readme should be updated with branch name and commit note)
- (Then do the git status, add, commit sequence to finalize)
- `git push origin L0XX-name` to push the branch to Github

Merge branch back into main and commit to Github

- `git checkout main` (goes back to main)
- `git merge --no-ff L0XX-name` (does merge into main that was just checked out)
- `git push origin main` to push the merged main to Github

Branch renaming

- When in (checked out) the branch: `git branch -m <new-branch-name>`
- When not in the branch: `git branch -m <branch-name> <new-branch-name>`
- To sync the remote to the new names, you have to push the `new-branch-name` and delete the `branch-name` **NOT TESTED YET**
    + `git push origin -u <new-branch-name>` (u resets the upstream branch)
    + `git push origin -d <branch-name>` (or -delete)

### Start Building App

L065a.HelloWorld: Clean and setup initial Hello World state
- (MB: Hello World seems like a simple starting state to confirm setup is working) 

L065b.HomePage: Add HomePage basic layout - built without props or state
- (MB: The starting point here is identifying the components and the component structure, without thinking about props or state. It's almost like creating a static html page for layout and control heirarchy.)
- (MB: It's like a pre-step for [Thinking in React: Step 1](https://reactjs.org/docs/thinking-in-react.html#step-1-break-the-ui-into-a-component-hierarchy). That article urges the  [single responsibility principle](https://en.wikipedia.org/wiki/Single-responsibility_principle).)

L069a.DirectoryStructure: Add directory structure and move components into it

L069b.HomePageComponents: Refactor HomePage into Directory and MenuItem components
- (MB: Static-like html is refactored into components and the location of data is determined.)
- (MB: The lowest level, MenuItem, is built first and will only contain props passed in. It is created as a const function with arrow sytax. Destructuring of the props is used for coding simplicity.)
- (MB: Next lowest level, Directory, is built to handle the array of MenuItem data. State is used (and hardcoded with values needed that were set in the original static-like html.) The .map function is used on the array in the state to build the MenuItem tags.)
