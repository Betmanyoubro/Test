# Instructions for __Git__

### __What is *Git*?__

### __*Git*__ is one of the version control systems, __*Git*__ is currently the absolute leader in popularity among version control systems.

## __1. Getting started with *Git*__

+ ### Introduce himself __*Git*__:

After installing Git, add the data: username and email address. To do this, enter the following commands in the terminal:

```sh
git config --global user.name "username"

git config --global user.email email
```

Now each action will be marked with a name and mail.

## __2. Getting started __*Git*__ with folders and files__

+ ### Creating a new repository:

__* The Git repository is a virtual repository for the project. It can store versions of files for access as needed.*__

__*Git*__ stores its files and history directly in the project folder. To create a new repository, you need to open a terminal, go to the project folder and run the init command. This will enable the application in that particular folder and create a hidden __ directory.git__, where the repository history and settings will be stored.

```sh
git init
```

+ ### Checking the repository status:

```sh
git status
```

__*status*__ is a command that displays information about the current state of the repository: is the information on it up-to-date, is there anything new that has changed, and so on.

+ ### Adding a file to the repository for version tracking:

After checking the repository status, we will see files that git does not track, they will be marked in red.
To add a single tracking file, enter the command:

```sh
git add file_name.file_format (example ---> git.md)
```
To add all the repository files to track them, enter the command:

```sh
git add -a
```

After that, we check - if everything is correct, then when re-checking the repository status, these files will be marked in green.

+ ### Creating a commit of repository files:

A commit is saving the current state of the project changes added to the indexed files section.

```sh
git commit -m "commit comment - description of the commit"
```

But before the __*git commit*__ command,  need to enter the __*git add*__ command to add ("index") changes to the project that will be saved during commit.

* ### Viewing the repository commit history:

To view all committed commits, you can use the commit history. It contains information about each completed commit of the project. You can request it using the command:

```sh
git log
```
if you add __*--oneline*__ to the command, there will be a simplified commit list:

```sh
git log --oneline
```

+ ### Moving between file commits:

To view changes in different versions of the file, run the __*git log*__ command, find the commit of interest, copy the first 4 characters of the commit index and run the command:

```sh
git chekout 78а1(<--- the first 4 characters of the commit index are enough)
```

In order to go to the latest version of the project, need to enter the name of the branch in which are working instead of the commit index:

```sh
git chekout master(<--- name_branch) 
```

##3. Getting started with project branches

### Branching

During the development of new functionality, it is considered good practice to work with a copy of the original project, which is called a branch. Branches have their own history and changes isolated from each other until you decide to merge the changes together. This happens for a number of reasons:

+ The already working, stable version of the file is saved.

+ Various new features can be developed in parallel by different programmers.

+ Developers can work with their own branches without the risk that the file base will change due to other people's changes.

+ In case of doubt, different implementations of the same idea can be developed in different branches and then compared.

* ### Viewing file branches:

```sh
git branch
```

After entering the command, we will see all the branches of the repository in the console-terminal and which branch we are on.

The branch we are on is marked with an asterisk, example: *master

* ### Creating a new branch

The main branch in each repository is called master. To create a new branch, enter the command:

```sh
git branch name_branch
```

But if, when entering the command, you specified __*the name of a branch*__ that already exists, you will get an error with the message that this branch with that name already exists!

+ ### Switching between branches

First, enter the command __*git branch*__ to view the names of all existing branches.

Find the right branch. enter the command:

```sh
git checkout name_branch
```

__*Git checkout*__ - allows you to switch between both remote and local branches. This is one way to gain access to the work of a colleague or co-author, providing higher collaboration productivity. However, it must be remembered that until you commit the changes, you will not be able to switch to another branch.

+ ### Merging branches

As an example, merge the __master__ branch with the __master_draft__ branch, need to be in the __master__ branch and enter the command:

```sh
git merge master_draft
```

+ ### Removing branches

To delete a branch, enter the command :

```sh
git branch -d name_branch
```