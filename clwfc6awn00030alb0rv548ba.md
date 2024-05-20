---
title: "Git GitHub-Day 2 of 40 days MERN Stack"
seoTitle: "Git and GitHub Basics: Day 2 MERN Stack"
seoDescription: "Learn Git and GitHub basics, including installation, configuration, staging, committing, and branching, as part of the 40-day MERN Stack journey"
datePublished: Mon May 20 2024 19:05:22 GMT+0000 (Coordinated Universal Time)
cuid: clwfc6awn00030alb0rv548ba
slug: git-github-day-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1716221437037/2829da29-b9d8-4174-a653-5ab207541be0.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1716231880950/2216bbd1-ab43-4ea1-a453-c79e8b2559fb.png
tags: github, git, mern, mern-stack, mern-stack-development

---

## Git and GitHub Introduction

[**Git**](http://git-scm.com) is a version control system that intelligently tracks changes in files. Git is particularly useful when you and a group of people are all making changes to the same files at the same time.

[GitHub](http://www.github.com) is a cloud-based platform where you can store, share, and work together with others to write code.

### How do Git & Github work together?

When you upload files to GitHub, you'll store them in a "Git repository." This means that when you make changes (or "commits") to your files in GitHub, Git will automatically start to track and manage your changes.

---

## Start your Journey

To get started with GitHub, you'll need to create a free personal account on [GitHub.com](http://github.com) and verify your email address.

Download Git from [git-scm.com/downloads](http://git-scm.com/downloads)

### Using Git with Command Line:

To start using Git, we are first going to open up our Command shell.

For Windows, you can use Git bash, which comes included in Git for Windows. For Mac and Linux you can use the built-in terminal.

The first thing we need to do, is to check if Git is properly installed & configure Git:

```bash
git --version
```

**Configure Git:**

```bash
git config --global user.name "daily-tech"
```

```bash
git config --global user.email "mail@thearnab.tech"
```

---

## Git Getting Started

### Creating Git Folder

```bash
mkdir myproject
cd myproject
```

*If you already have a folder/directory you would like to use for Git: Navigate to it in command line.*

### Initialize Git

Once you have navigated to the correct folder, you can initialize Git on that folder:

```bash
git init
```

### Git Adding New Files

You just created your first local Git repo. But it is empty. So let's add some files, or create a new file using your favourite text editor. Then save or move it to the folder you just created.

---

## Git Tracking & Staging

Git is aware of the file you saved in the previous step, but has not added it to our repository!  
Files in your Git repository folder can be in one of **2** states:

* **Tracked** - files that Git knows about and are added to the repository.
    
* **Untracked** - files that are in your working directory, but not added to the repository.
    

When you first add files to an empty repository, they are all **untracked**. To get Git to track them, you need to **stage** them, or add them to the **staging environment.**

As you are working, you may be adding, editing and removing files. But whenever you hit a **milestone** or **finish** a part of the work, you should add the files to a **Staging Environment.**

Staged files are files that are ready to be **committed** to the repository you are working on.

```bash
git add index.html
```

```bash
git add --all
```

*Using --all instead of individual filenames will stage all changes (new, modified, and deleted) files.*

---

## Git Commit

Now all files are added to the **Staging Environment**, and we are ready to do our first **commit**.

Since we have finished our work, we are ready move from **stage** to **commit** for our **repo**.

Adding **commits** keep track of our progress and changes as we work. Git considers each commit change point or "**save point**". It is a point in the project you can go back to if you find a bug, or want to make a change

When we commit, we should always include a ***message***.

```bash
git commit -m "Hello World!"
```

---

## Git Branches

Working with Git Branches

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1716231316864/d84992a1-977b-40b8-8fef-611acf1c80b9.png align="center")

### New Git Branch

Let add some new features to our index.html page. We are working in our local repository, and we do not want to disturb or possibly wreck the main project.

So we create a new **branch:**

```bash
git branch hello-world
```

Now we created a new branch called “**hello-world**”

**Checkout** is the command used to check out a branch. Moving us from the current branch, to the one specified at the end of the command:

```bash
git checkout hello-world
```

We have the **hello-world** ready, and so let's **merge** the **master**(**main**) and hello-world branches. First, we need to change to the **master**(**main**) branch:

```bash
git checkout master
```

```bash
git merge hello-world
```

Now you have a better understanding of how branches and merging works. Time to start working with a remote repository!

Stay Tuned....

Signing off. Have a great day.