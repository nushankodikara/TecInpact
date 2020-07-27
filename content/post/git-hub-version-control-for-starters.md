---
title: "Git Hub Version Control for Starters"
date: 2020-07-27T06:00:00+05:30
Description: ""
Tags: ["Windows","Git Hub","Guide"]
Categories: []
DisableComments: false
---

# Introduction

Now let's take an start on our project directories, we as programmers and developers, always run into certain problems regarding our folder structures, corrupted files, need to undo but unable to do that because we made a terrible mistake and so on. Is there a way which we can solve this? Yes it is! that's called version controlling, Here we'll be able to backup our codes with version numbers and retrieve anytime we want, and when working with several developers in a single project, we'll be able to collaborate and code the same project simultaneously with these things, so without much explanation let's get into it.

# What’s a version control system?
A version control system, or VCS, tracks the history of changes as people and teams collaborate on projects together. As the project evolves, teams can run tests, fix bugs, and contribute new code with the confidence that any version can be recovered at any time. Developers can review project history to find out:

* Which changes were made?
* Who made the changes?
* When were the changes made?
* Why were changes needed?

# Why Git?
There are many more version control systems but we are using GIT because it's free and it's what most of the developers use. and also it has many more features like web-hosting and many more, which we're going to explore in a later date.

# What’s a repository?
Consider a repository as a project. and that's the most simplistic explanation on what's a repository. Why they are called repositories you ask? That's just a fancy name git uses and That's all. Alongside with the repositories, there is a system to track down the changes, so if you need to rollback to a previous version of your project, you can do it in a matter of seconds and there are no limitations for this process.

# What services we use
There are many hit services like gitbucket github gitlabs so on... but we're using github today, not for a real reason but it's my favorite git service and I use it on my personal projects allot.

# How do I start
There are many ways you can start, you can use a full GUI based application like github desktop or the command line GIT or extensions for VSCode too.. now let's download git first, you can use https://desktop.github.com/ This link or just got to your appstore on pc for linux and mac users. Anyway you need a git client on your machine install it, restart the machine and you're good to go. Also goto www.github.com and create your account before starting, in anytime you'll come-up with a login section, which you have to login with your email and password.

# Github CLI

Let's start with the command line interface, you have to start a command line interface in your working directory. it's different from machine to machine but you should probably know by now how it's done, otherwise I don't think it's a good idea to continue. Anyway if you're running into problems while using the command line, skip this section and follow along with the GUI base version.

By using git command line you can come-up with this section of documentation

```
usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone             Clone a repository into a new directory
   init              Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add               Add file contents to the index
   mv                Move or rename a file, a directory, or a symlink
   restore           Restore working tree files
   rm                Remove files from the working tree and from the index
   sparse-checkout   Initialize and modify the sparse-checkout

examine the history and state (see also: git help revisions)
   bisect            Use binary search to find the commit that introduced a bug
   diff              Show changes between commits, commit and working tree, etc
   grep              Print lines matching a pattern
   log               Show commit logs
   show              Show various types of objects
   status            Show the working tree status

grow, mark and tweak your common history
   branch            List, create, or delete branches
   commit            Record changes to the repository
   merge             Join two or more development histories together
   rebase            Reapply commits on top of another base tip
   reset             Reset current HEAD to the specified state
   switch            Switch branches
   tag               Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch             Download objects and refs from another repository
   pull              Fetch from and integrate with another repository or a local branch
   push              Update remote refs along with associated objects

'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
See 'git help git' for an overview of the system.
```

now With this section, you're pretty much good to go it's self explanatory, Let's get started and I'll show you some commands, not everything, only what you would need in your day-to-day programming career.

## Let's explore Basic commands

* **git init** - initializes a brand new Git repository and begins tracking an existing directory. It adds a hidden subfolder within the existing directory that houses the internal data structure required for version control.

* **git clone** - creates a local copy of a project that already exists remotely. The clone includes all the project’s files, history, and branches.

* **git add** - stages a change. Git tracks changes to a developer’s codebase, but it’s necessary to stage and take a snapshot of the changes to include them in the project’s history. This command performs staging, the first part of that two-step process. Any changes that are staged will become a part of the next snapshot and a part of the project’s history. Staging and committing separately gives developers complete control over the history of their project without changing how they code and work.

* **git commit** - saves the snapshot to the project history and completes the change-tracking process. In short, a commit functions like taking a photo. Anything that’s been staged with git add will become a part of the snapshot with git commit.

* **git status** - shows the status of changes as untracked, modified, or staged.

* **git branch** - shows the branches being worked on locally.

* **git merge** - merges lines of development together. This command is typically used to combine changes made on two distinct branches. For example, a developer would merge when they want to combine changes from a feature branch into the main branch for deployment.

* **git pull** - updates the local line of development with updates from its remote counterpart. Developers use this command if a teammate has made commits to a branch on a remote, and they would like to reflect those changes in their local environment.

* **git push** - updates the remote repository with any commits made locally to a branch.

## Branches?
Consider them as parallel universes. Branches are the same copy of code but modified differently, you can merge two branches anytime you want and also you can create unlimited branches of a repository

## How GitHub works

" GitHub builds collaboration directly into the development process. Work is organized into repositories, where developers can outline requirements or direction and set expectations for team members. Then, using the GitHub flow, developers simply create a branch to work on updates, commit changes to save them, open a pull request to propose and discuss changes, and merge pull requests once everyone is on the same page."

## Flow
Here we're discussing about the work flow of the github, also we can call this steps to make a github repository for a project.

The GitHub flow is a lightweight, branch-based workflow built around core Git commands used by teams around the globe—including ours.

The GitHub flow has six steps, each with distinct benefits when implemented:

* Create a branch: Topic branches created from the canonical deployment branch (usually main) allow teams to contribute to many parallel efforts. Short-lived topic branches, in particular, keep teams focused and results in quick ships.
* Add commits: Snapshots of development efforts within a branch create safe, revertible points in the project’s history.
* Open a pull request: Pull requests publicize a project’s ongoing efforts and set the tone for a transparent development process.
* Discuss and review code: Teams participate in code reviews by commenting, testing, and reviewing open pull requests. Code review is at the core of an open and participatory culture.
* Merge: Upon clicking merge, GitHub automatically performs the equivalent of a local ‘git merge’ operation. GitHub also keeps the entire branch development history on the merged pull request.
* Deploy: Teams can choose the best release cycles or incorporate continuous integration tools and operate with the assurance that code on the deployment branch has gone through a robust workflow.

## Can we code now?
Of course, let's get into it. Now i'll provide some examples on how we can use the github command-line interface for our needs.

### Contributing to a current repository
```
# download a repository on GitHub.com to our machine
git clone https://github.com/me/repo.git

# change into the `repo` directory
cd repo

# create a new branch to store any new changes
git branch my-branch

# switch to that branch (line of development)
git checkout my-branch

# make changes, for example, edit `file1.md` and `file2.md` using the text editor

# stage the changed files
git add file1.md file2.md

# take a snapshot of the staging area (anything that's been added)
git commit -m "my snapshot"

# push changes to github
git push --set-upstream origin my-branch
```

### Start a new repository and publish it to GitHub
Before this step, goto github and create a new repository, It's simple as it sounds and I'm not showing it here.
```
# create a new directory, and initialize it with git-specific functions
git init my-repo

# change into the `my-repo` directory
cd my-repo

# create the first file in the project
touch README.md

# git isn't aware of the file, stage it
git add README.md

# take a snapshot of the staging area
git commit -m "add README to initial commit"

# provide the path for the repository you created on github
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git

# push changes to github
git push --set-upstream origin main
```

### Contribute to an existing branch on GitHub
```
# assumption: a project called `repo` already exists on the machine, and a new branch has been pushed to GitHub.com since the last time changes were made locally

# change into the `repo` directory
cd repo

# update all remote tracking branches, and the currently checked out branch
git pull

# change into the existing branch called `feature-a`
git checkout feature-a

# make changes, for example, edit `file1.md` using the text editor

# stage the changed file
git add file1.md

# take a snapshot of the staging area
git commit -m "edit file1"

# push changes to github
git push
```

And that's all for the command line, you can visit github guide pages on how you can improve and use advanced functionality of github, If you're interested, I can also make a post on advanced github functions, so let me know in the comments wether you need one.

# Github Desktop

Here we come to a fun part, Github GUI version is more fun to explore and use, It has everything a user needs with a guide on hand, First goto https://desktop.github.com/ and download your copy of github. And you can use it right on.

![Github](https://desktop.github.com/images/github-desktop-screenshot-windows.png)

This application is straight forward but follows the same workflow as the github CLI version, in case you didn't read it and managed to get here straight, you can find it here  again.

## Flow
Here we're discussing about the work flow of the github, also we can call this steps to make a github repository for a project.

The GitHub flow is a lightweight, branch-based workflow built around core Git commands used by teams around the globe—including ours.

The GitHub flow has six steps, each with distinct benefits when implemented:

* Create a branch: Topic branches created from the canonical deployment branch (usually main) allow teams to contribute to many parallel efforts. Short-lived topic branches, in particular, keep teams focused and results in quick ships.
* Add commits: Snapshots of development efforts within a branch create safe, revertible points in the project’s history.
* Open a pull request: Pull requests publicize a project’s ongoing efforts and set the tone for a transparent development process.
* Discuss and review code: Teams participate in code reviews by commenting, testing, and reviewing open pull requests. Code review is at the core of an open and participatory culture.
* Merge: Upon clicking merge, GitHub automatically performs the equivalent of a local ‘git merge’ operation. GitHub also keeps the entire branch development history on the merged pull request.
* Deploy: Teams can choose the best release cycles or incorporate continuous integration tools and operate with the assurance that code on the deployment branch has gone through a robust workflow.

GitHub Desktop is an open source [Electron](https://electron.atom.io)-based
GitHub app. It is written in [TypeScript](http://www.typescriptlang.org) and
uses [React](https://facebook.github.io/react/).

![GitHub Desktop screenshot - Windows](https://cloud.githubusercontent.com/assets/359239/26094502/a1f56d02-3a5d-11e7-8799-23c7ba5e5106.png)

## Where can I get it?

Download the official installer for your operating system:

 - [macOS](https://central.github.com/deployments/desktop/desktop/latest/darwin)
 - [Windows](https://central.github.com/deployments/desktop/desktop/latest/win32)
 - [Windows machine-wide install](https://central.github.com/deployments/desktop/desktop/latest/win32?format=msi)

You can install this alongside your existing GitHub Desktop for Mac or GitHub
Desktop for Windows application.

**NOTE**: there is no current migration path to import your existing
repositories into the new application - you can drag-and-drop your repositories
from disk onto the application to get started.

### Beta Channel

Want to test out new features and get fixes before everyone else? Install the
beta channel to get access to early builds of Desktop:

 - [macOS](https://central.github.com/deployments/desktop/desktop/latest/darwin?env=beta)
 - [Windows](https://central.github.com/deployments/desktop/desktop/latest/win32?env=beta)

### Community Releases

There are several community-supported package managers that can be used to
install GitHub Desktop:
 - Windows users can install using [Chocolatey](https://chocolatey.org/) package manager:
      `c:\> choco install github-desktop`
 - macOS users can install using [Homebrew](https://brew.sh/) package manager:
      `$ brew cask install github`

Installers for various Linux distributions can be found on the
[`shiftkey/desktop`](https://github.com/shiftkey/desktop) fork.

Arch Linux users can install the latest version from the
[AUR](https://aur.archlinux.org/packages/github-desktop-bin/).

## Is GitHub Desktop right for me? What are the primary areas of focus?

[This document](https://github.com/desktop/desktop/blob/development/docs/process/what-is-desktop.md) describes the focus of GitHub Desktop and who the product is most useful for.

And to see what the team is working on currently and in the near future, check out the [GitHub Desktop roadmap](https://github.com/desktop/desktop/blob/development/docs/process/roadmap.md).

## I have a problem with GitHub Desktop

Note: The [GitHub Desktop Code of Conduct](https://github.com/desktop/desktop/blob/development/CODE_OF_CONDUCT.md) applies in all interactions relating to the GitHub Desktop project.

First, please search the [open issues](https://github.com/desktop/desktop/issues?q=is%3Aopen)
and [closed issues](https://github.com/desktop/desktop/issues?q=is%3Aclosed)
to see if your issue hasn't already been reported (it may also be fixed).

There is also a list of [known issues](https://github.com/desktop/desktop/blob/development/docs/known-issues.md)
that are being tracked against Desktop, and some of these issues have workarounds.

If you can't find an issue that matches what you're seeing, open a [new issue](https://github.com/desktop/desktop/issues/new/choose),
choose the right template and provide us with enough information to investigate
further.

## The issue I reported isn't fixed yet. What can I do?

If nobody has responded to your issue in a few days, you're welcome to respond to it with a friendly ping in the issue. Please do not respond more than a second time if nobody has responded. The GitHub Desktop maintainers are constrained in time and resources, and diagnosing individual configurations can be difficult and time consuming. While we'll try to at least get you pointed in the right direction, we can't guarantee we'll be able to dig too deeply into any one person's issue.

## How can I contribute to GitHub Desktop?

The [CONTRIBUTING.md](./.github/CONTRIBUTING.md) document will help you get setup and
familiar with the source. The [documentation](docs/) folder also contains more
resources relevant to the project.

If you're looking for something to work on, check out the [help wanted](https://github.com/desktop/desktop/issues?q=is%3Aissue+is%3Aopen+label%3A%22help%20wanted%22) label.

## More Resources

See [desktop.github.com](https://desktop.github.com) for more product-oriented
information about GitHub Desktop.

## I still didn't got it

Go ahead and Create a repository in github and download then login to the Desktop client, you can see your repositories in the left hand side and using the GUI, clone it. you can then work on your project as usual and come back to github application to see your changes and from here on you can commit from the left bottom button and push to your repository from the top button, and you're good to go.

# Conclusion

Github is the favorite of most of the developers these days due to their functionalities, I'll show you how you can use these specialties in the near future and until then, be safe and stay home.