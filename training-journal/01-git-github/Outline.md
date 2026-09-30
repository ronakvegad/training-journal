# dev-journal
 
random notes as i learn stuff. mostly for me, not polished.
 
---
 
## Git & GitHub (done - Sep 2026)
## DAY - 01 --- 26-09-2026
### Section - 1 & 2: Version Control Basics
- git = tracks changes to files over time, can go back to any point
- basically saves snapshots not just diffs (kinda, its more complex but thats the mental model)
### install
- windows: git bash comes with the installer, use that instead of cmd
- mac: `brew install git` or just xcode command line tools installs it
- linux: `sudo apt install git` (ubuntu/debian)
### setup workspace
- pick a folder, `git init` inside it = starts tracking
- or `git clone <url>` if repo already exists somewhere
- set username/email once globally so commits arent anonymous:
```
  git config --global user.name "your name"
  git config --global user.email "your email"
```
 
### first commit
- `git add <file>` or `git add .` for everything = staging
- `git commit -m "message"` = actually saves the snapshot
- staging vs committing tripped me up at first — staging is just "prepping" what goes in the next commit
### full commit flow
working dir -> staged -> committed -> (pushed to remote)
- `git status` shows you where things are in this flow, check it before every commit tbh
### reviewing changes
- `git diff` = see what changed before staging
- `git diff --staged` = see what's staged vs last commit
- `git log` = commit history
### missing config stuff
- .gitignore file — stop tracking node_modules, .env, build folders etc
- forgot this once and committed my .env with API keys lol. add .gitignore FIRST thing in any new project
### github
- github = remote hosting for git repos, not the same thing as git itself
- made account, created ssh key or just used https+token for auth
### pushing local -> github
```
git remote add origin <repo-url>
git push -u origin main
```
- -u sets upstream so after this you can just do `git push`
### editing + committing from github web
- can edit small stuff directly on github, auto-creates a commit
- fine for quick fixes, not for real dev work
### pulling from remote
- `git pull` = fetch + merge in one go
- do this BEFORE you start working if repo is shared / multi-device, avoids merge conflict headaches
### git status (again bc it matters)
- run this constantly, tells you staged/unstaged/untracked files
- good habit before every add/commit
---
 
## still confused about
- rebase vs merge — get the theory but havent actually used rebase for real yet
- when exactly to use branches vs just working on main for solo projects
## next up
- branching + PR workflow
- resolving actual merge conflicts (only done fake ones so far)


## DAY - 02 --- 27-09-2026

## Section - 3 : Fork And Clone

Forking Is basically just making a copy of a repository under your own github account , so like after the fork you can do your own new changes on that repo and the owner can also make their commits in the same repo.

# How to clone anything from github
```
git clone "URL of the repo"
```
# Git Logs
- `git log` = shows commit history (newest first) - hash, author, date, message
- `git log --author="name"` = filter by who committed

- in the same branch if i want to comapre the commits that i have already given and i want to compare the any two commits so we can do like that
 
 "git diff "starting 8 digits from starting from each git log commits""

# git annotate "file name"
- timing and changes whatever happens
- detail changes about any particular file
- 'Gitlens' this is an EXTENSTION who tells the users exact changes about each lines in the file.
# git show


# making changes into any specific repo and commiting

- if we doesnt wanted to ad everytime whatever changes we make and just directly wanted to do commit so we can use this command

- git commmit -a "message"

# undoing changes and reverting commits

- for discarding the changes before the commiting part  we jsut use this command "git checkout --(file name)"

- if we have already staged our changes into our working directory
just use this command - "git reset HEAD (file name)"
and then do agian the - "git checkout ..."


 ##   Working with Branches

### 1. Good Version Control Practices
- Commit small and often, with one logical change per commit
- Write clear messages, e.g. `Add login validation`, not `changes`
- Never work directly on `main`; use branches

### 2. What is a Branch?
- A separate line of development, like a copy where you can experiment safely
- `main` stays stable while features are built on other branches

### 3. Creating a Branch (Git)
```bash
git branch                  # list branches
git branch feature-x        # create
git checkout feature-x      # switch
git checkout -b feature-x   # create + switch
```

### 4. Creating a Branch (GitHub)
- Use the branch dropdown → type a name → **Create branch**
- Then `git fetch` and `git checkout <branch>` locally

### 5. .gitignore
- Tells Git which files to skip (`node_modules/`, `.env`, `*.log`)
```
node_modules/
.env
*.log
```

### 6. Syncing Branches
```bash
git push -u origin feature-x   # push a new branch
git pull                       # get latest changes
git fetch                      # download without merging
```

### 7. Graph Branches in Terminal
```bash
git log --oneline --graph --all
```

### 8. Merging Branches
```bash
git checkout main
git merge feature-x

## for deleting any branch 

git branch -d "branch name"



```
- If there is a conflict, fix the files, then `git add .` and `git commit`

### 9. Pull Requests (GitHub)
- A PR asks to merge your branch into `main`
- Flow: push branch → open PR → review → merge → delete branch

###  Quick Flow
`branch → commit → push → pull request → merge`

## Merge Conflicts
## Collabration in github