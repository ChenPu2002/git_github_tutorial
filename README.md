# Git/Github tutorial for personal and group development

## Table of Contents
- [Introduction](#introduction)
- [Configuring Git](#configuring-git)
- [Basic Git Commands](#basic-git-commands)
- [Using GitHub](#using-github)
- [Collaboration and Branching](#collaboration-and-branching)

## Introduction
Why we need git? The first time I learnt Git was in a course, we were required to submit our course project with github. However, at that time, Git and Github were ...

## Configuring Git
Before you start using Git, you need to configure it. Open your terminal and set your name and email address with the following commands:

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

## Basic Git Commands
Here are some basic Git commands to get you started:

- `git init`: Initializes a new Git repository.
- `git add .`: Adds all changed files in the current directory to the staging area.
- `git commit -m "Commit message"`: Commits the staged files with a message describing the changes.
- `git status`: Shows the status of changes in the current repository.
- `git log`: Displays the commit history.

These commands are essential for basic Git operations.

## Using GitHub
To use GitHub, create an account at [github.com](https://github.com). Once your account is set up, you can create new repositories, clone existing ones, and push your local repositories to GitHub.

Here's how to push a local repository to GitHub:

1. Create a new repository on GitHub.
2. Copy the repository URL provided by GitHub.
3. In your local repository, run:

```bash
git remote add origin <repository-URL>
git push -u origin master
```

## Collaboration and Branching

Collaborating on projects with Git involves managing branches:

- `git branch`: Lists all local branches.
- `git branch <branch-name>`: Creates a new branch.
- `git checkout <branch-name>`: Switches to the specified branch.
- `git merge <branch-name>`: Merges the specified branch into the current branch.

Use branches to isolate development work without affecting other parts of the project.
