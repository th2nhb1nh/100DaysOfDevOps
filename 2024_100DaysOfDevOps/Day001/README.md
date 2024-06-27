# Day 1: Advanced Git and GitHub Workflows

## Objectives
- Understand and apply advanced Git commands.
- Learn branching strategies and how to manage complex workflows.
- Practice collaboration using pull requests and code reviews on GitHub.

## Topics Covered
1. Advanced Git Commands
    - Rebasing
    - Cherry-Picking
    - Stashing
    - Resetting
    - Reflog
2. Branching Strategies
    - Git Flow
    - GitHub Flow
    - Trunk-Based Development
3. Collaborating on GitHub
    - Pull Requests
    - Code Reviews

## Learning Plan (1-2 Hours)

### Introduction
- Brief overview of advanced Git commands and workflows (10 minutes).

### Advanced Git Commands
1. **Rebasing** (20 minutes)
    - Watch a tutorial or read documentation on `git rebase` and `git rebase -i`.
    - Practice rebasing a feature branch onto the main branch.
        ```sh
        git checkout -b feature-branch # create and checkout to the new branch
        git add .
        git commit -m "Commit message for feature-branch"
        git push --set-upstream origin feature-branch # git push and change up-stream to the tip of the new branch
        git rebase master # change the base of the feature-branch to the tip of the master branch, while still keep the history commits
        ```
    - Interactive Rebase Example:
        ```sh
        git rebase -i HEAD~3
        ```
    - **Notes:**
        - `rebase`: imagine like changing the base of the feature 
        ![alt text](<Git Rebase Tutorial.png>)
        - `merge`: add text
        

2. **Cherry-Picking** (10 minutes)
    - Identify a commit from one branch and apply it to another branch.
        ```sh
        git checkout another-branch
        git cherry-pick <commit-hash>
        ```
    - **Notes:**
        - 

3. **Stashing** (10 minutes)
    - Stash uncommitted changes and apply them later.
        ```sh
        git stash
        git stash apply
        ```
    - **Notes:**
        - 

4. **Resetting** (10 minutes)
    - Experiment with different reset options.
        ```sh
        git reset --soft <commit-hash>
        git reset --mixed <commit-hash>
        git reset --hard <commit-hash>
        ```
    - **Notes:**
        - 

5. **Reflog** (10 minutes)
    - Use `git reflog` to recover a lost commit.
        ```sh
        git reflog
        ```
    - **Notes:**
        - 

### Branching Strategies
6. **Branching Strategies** (10 minutes)
    - Study different branching strategies (Git Flow, GitHub Flow, Trunk-Based Development).
    - **Notes:**
        - 

### Collaborating on GitHub
7. **Pull Requests** (10 minutes)
    - Create a new repository on GitHub.
    - Create a pull request and write a comprehensive description.
    - **Notes:**
        - 

8. **Code Reviews** (10 minutes)
    - Invite a collaborator to review your pull request.
    - Review a collaborator’s pull request and provide feedback.
    - **Notes:**
        - 

## Hands-On Exercises (1 Hour)

### Exercise 1: Advanced Git Commands (20 minutes)
- Create a repository and simulate a workflow involving rebasing, cherry-picking, and stashing.
- **Notes:**
    - 

### Exercise 2: Branching Strategies (20 minutes)
- Implement Git Flow or GitHub Flow on a small project.
- **Notes:**
    - 

### Exercise 3: GitHub Collaboration (20 minutes)
- Create a pull request on GitHub, request a review, and perform a code review.
- **Notes:**
    - 

### Evening Review
9. **Review and Reflect** (10 minutes)
    - Summarize what you've learned about advanced Git commands, branching strategies, and collaboration on GitHub.
    - Reflect on any challenges faced during hands-on exercises and how to overcome them.
    - Plan for the next day’s topic: Advanced Linux Command-Line Operations and Scripting.
    - **Notes:**
        - 
