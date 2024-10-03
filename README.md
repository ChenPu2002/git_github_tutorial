# Git/Github tutorial for personal and group development

## Table of Contents
- [Introduction](#introduction)
- [History of Git](#history-of-git)
- [Configuring Git](#configuring-git)
- [Basic Git Commands](#basic-git-commands)
- [Connection and Authentication](#connection-and-authentication)
- [Starting a new repository](#starting-a-new-repository)
- [Collaboration and Branching](#collaboration-and-branching)

## Introduction
Why we need git? The first time I learnt Git was in a course. However, at that time, Git and Github were just tools for me to submit our project. Naturally, we use add file by upload in Github and download the code by zip. Luckily, the project was not very large and we can manage the code without Git.

One year later, I did another course project and still no one in my group knew how to use Git. So we just shared our code through Wechat. It was a disaster as the scale of the project had become larger. I had to merge all our code manually as I was the major develeper and it was very hard to track the changes made by my groupmates. I realized that I need to use Git and Github for development in the future. So I started to learn Git and Github by myself in the spare time.

And then for the most recent course project, I used Git and Github to manage our code in the whole time. It was a great experience. I could track the changes, manage the code and collaborate with my group members easily. I realized that Git and Github are very useful tools for both personal and group development. So I decided to write this tutorial to help myself and others to learn Git and Github.

## History of Git
Git is originally developed by Linus Torvalds, the creator of the Linux kernel. Originally, the Linux kernel source code was distributed using email patches and archives. However, this approach was not scalable for a large project like the Linux kernel. Linus Torvalds decided to create a distributed version control system that could handle the demands of the Linux kernel development process. This system became Git.

<figure>
    <img src="image/Linus.jpg" alt="Linus Torvalds" style="width:80%">
    <figcaption> Linus is an elegant and easy-going guy. <strong><em>He won't give the middle finger in public.</em></strong></figcaption>
</figure>

## Configuring Git
Before you start using Git, you need to configure it. Open your terminal and set your name and email address with the following commands:

```bash
git config --global user.name "Your Name"
```
```bash
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

## Connection and Authentication 
To use GitHub, create an account at [github.com](https://github.com). Once your account is set up, you can create new repositories, clone existing ones, and push your local repositories to GitHub.
On your local machine, you can connect Github with HTTPS by default (which is a remote to you). However, it would be hard to use as you need to input your password to check your identity. Thus, it would easier to connect Github by SSH. Your need to create a public and private key in .ssh folder in your machine and then copy it to Github.

Use the following line to test the connection and authentication with Github (SSH),
```bash
ssh -T git@github.com
```


## Starting a New Repository
Create a new repository on the command line. To let git managing your folder, you need to ensure that .git is exsiting in the folder itself or its parent folder.
To do that, you should use git init:
```bash
git init
```

### White List Strategy:
Then, you need to stage all the files you want to manage with git by git add:
For example, if you want to add README.md to stage:
```bash
git add README.md
```
### Black List Strategy:
or if you want to add all the files in the current folder, use
```bash
git add .
```
If you have any file you don't want to add to the git, use .gitignore file to maintain the black list. Thus, all the files in .gitignore will not be tracked by git.

```bash
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:<name>/<project>.git
git push -u origin main
```
…or push an existing repository from the command line
```bash
git remote add origin git@github.com:<name>/<project>.git
git branch -M main
git push -u origin main
```

## Collaboration and Branching

Collaborating on projects with Git involves managing branches:

- `git branch`: Lists all local branches.
- `git branch <branch-name>`: Creates a new branch.
- `git checkout <branch-name>`: Switches to the specified branch.
- `git merge <branch-name>`: Merges the specified branch into the current branch.

Use branches to isolate development work without affecting other parts of the project.

## Updating Local Branch from Remote (Github)

```bash
git pull # = git fetch + git merge
```
If there is any merge conflict between remote code and local code, error will appear and you have to solve the merge conflict manully.

