## Git and GitHub Notes

### Introduction

#### Git

- **Definition**: Git is a distributed version control system for tracking changes in source code during software development.
- **Key Features**:
  - Tracks history of changes.
  - Supports branching and merging.
  - Distributed architecture.
  - Efficient handling of large projects.

#### GitHub

- **Definition**: GitHub is a cloud-based hosting service for managing Git repositories with added functionalities for collaboration.
- **Key Features**:
  - Repository hosting.
  - Collaboration tools (issues, pull requests, etc.).
  - GitHub Actions for CI/CD.
  - Version control with Git integration.

![Git vs GitHub](./git_v_github.png)

---

## Git Basics

### Installation

- Install Git from [git-scm.com](https://git-scm.com).
- Verify installation:
  ```bash
  git --version
  ```

### Git Configuration

```bash
# Set global configuration for user name and email
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"

# Use Visual Studio Code as default editor
git config --global core.editor "code --wait"  

# View configuration
git config --list
```

### Initialize Repository
  ```bash
  # initialize a new repository in the current directory
   git init

   # clone a repo
   git clone
```
### stage changes 
```bash
git add [filename]    # Add specific file
git add .               # Add all 
```

 

  ### check status of the repository
  ```bash 
  git status     #state changes before committing
  git status -s   # Show status in short format
  git reset <file>  # Unstage a file

   # Show differences 
   git diff <file>   # Show diff b/w the working directory and the latest commit
   git diff --staged  # Show differences between staging area and the latest commit
  ```
  ---
## Commit changes

```bash
git commit -m "Commit message"
git commit -am "Commit message"  # Commit changes with all tracked (modified) files
git commit --amend  # Modify last commit message
```

#### Reset commits

```bash
git reset --soft HEAD~1  # Reset to previous commit, keep changes staged
git reset --hard HEAD~1  # Reset to previous commit and discard changes
```
#### View commit history

```bash
git log
git log --oneline  # Show
git log --graph  # Show commit history with a graph
```

---

## Git Branching & Merging 

  ```bash
  git branch # list all branches
  git branch <branch-name>  # new branch 
  git checkout <branch-name> # switch to a branch 
  git checkout -b <branch-name>  # create & switch to a new branch 

  git branch -m <old-branch> <new-branch>   # rename:
  git branch -d branch-name  # delete a branch :
  ```

 ### Merging:
  ```bash
  git checkout master  # switch to master branch
  git merge <branch-name>
  
  #Note If both branches make changes to the same files, it's result in a conflict
  ```
### Resolving Merge Conflicts
1. Edit files with conflict markers:
  ```bash
<<<<<<< HEAD
Local changes
=======
Incoming changes
>>>>>>> branch-name
  ```
2. Stage resolved files

3. Commit changes

---

## Synchronizing with Remote Repository
```bash
# Connecting to a Remote Repository
git remote add origin <repository-url>

# Push all changes to a branch
git push origin <branch-name>  
```

### Fetch and Merge Changes

```bash
git fetch origin <branch-name>  # Fetch changes from remote branch
git merge origin/<branch-name>  # Merge changes from remote branch into current branch
```

### Pull Changes

```bash
git pull origin <branch-name>  # Fetch and merge changes from remote branch
```

### Delete Branches

```bash
git branch -d <branch-name>  # Delete a local branch
git push origin --delete <branch-name>  # Delete a remote branch
```
## Advanced Techniques
1.Stashing
```bash
git stash  # Stash changes temporarily
git stash list  # List all stashed changes
git stash pop  # Apply and remove 
```
2.Open Contribution
```bash 
  fork <repository-url>  # Fork a repository
  git clone <fork-url>  # Clone your fork
  git checkout -b <feature-branch>  # Create a new branch for your feature

  # Make changes and commit them
  git push origin <feature-branch>  # Push your feature branch to your fork

  # Create a pull request by GitHub
```
---

### ssh Key Generation
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub
````
add more point 
