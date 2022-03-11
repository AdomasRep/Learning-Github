# [Git & Github Tutorial](https://www.youtube.com/watch?v=RGOj5yH7evk&list=WL&index=10)

I believe only watching the tutorial would be useless. Therefore, I followed all the steps on my computer (index.html and README.md) and made a summary of the things I learned. I am storing this file here with the intention to learn additional [text formating tricks](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax). 

## Terms

* **Git** - free and open source version control system, it allows to track changes made to the code, documents and etc.
* **Github** - website is a place where you host your repositories online 
* **Directory** - folder 
* **CLI** - Command Line Interface
* **cd** - change directory when moving through folders ( __cd "directory"__ moves to the chosen directory. __cd ..__ moves one directory back)
* **Repository** - A project/ a folder where the project is kept. 

```
NOTE - you cannot have bold text or bullet points in the distinct block
```

## Main Git Commands

* **git clone** - brings a repository that is hosted somewhere like Github into a folder on your local machine. 
* **git add** - tracks files and changes in Git. You can either do *git add "file name"* to track changes in the certain file or *git add .* to track changes in all the files. 
* **git commit** - saves files with changes in Git (**not in Github**). When using this command, you **have** to add a message describing the changes: *git commit -m "message"*. If file was modified (**not created**), you can do *git commit -am "message"* to add and commit changes in one line of code. 
* **git push** - uploads Git commits to a remote repository, like Github. 
* **git pull** - downloads changes from a remote repository to your local machine. 

## Creating a Repository Locally

First, create an empty directory locally. When inside that directory, do *git init*, which will initialize an empty git repository. At that point, creating a new file, making changes to it, adding and committing them is possible. However, it is impossible to push those changes to Github. 

The tutorial describes one way to push those changes to Github. You have to manually create a new repository in Github (which is titled the same as the local directory) and then do:
```
    git remote add origin “Link to that empty repository in Github”
```
Finally, it is possible to push all the changes to Github.

## Branching

If you work on one code all of the commits will be in the master branch. However, if you create a new branch, commits saved in that branch won’t appear in the master branch and vice versa. It’s very common when working with many people on the same code/project. *git branch* – shows all the existing branches (here only one exists) and * indicates on which branch you are. 

![Branch](https://github.com/AdomasRep/Learning-Github/blob/main/Branch.png)

*git checkout "name of a branch"* is used to switch between branches. While, *git checkout -b “name of a new branch”* creates a new branch and swithces to that branch. 

![Checkout](https://github.com/AdomasRep/Learning-Github/blob/main/Checkout%20(create%20a%20new%20branch).png)

*git diff “branch to compare to”* gives difference between branches. 

![Difference](https://github.com/AdomasRep/Learning-Github/blob/main/Difference%20between%20branches.png)

Usually after making changes in the new branch, those changes are merged to the master branch. At that point new branch becomes useless and has to be deleted. This is done by *git branch -d “branch name”*

![Delete](https://github.com/AdomasRep/Learning-Github/blob/main/Delete%20branch.png)

## Merging Errors

It happens, if you make changes to the same line in different branches and try to merge those branches. First of all, it doesn’t allow to move to the other branch if those changes were not committed. You need to either commit those changes, or stash them (not discussed in the tutorial, but basically means storing changes somewhere without committing them to git). There are few options to tackle the conflicts. Visual Studio Code (maybe some others as well), allows to tackle the conflict manually or choose the code from the certain branch and then it adapts the code automatically. 

## Undoing

There are number of stages at which you might want to undo the changes you made to the file. 

* If changes were added but not yet committed, then do: *git reset* (if you want to undo changes for a certain file, add the file name) 

![reset](https://github.com/AdomasRep/Learning-Github/blob/main/Reset.png)

* If changes were added and commited, then do: *git reset HEAD~1*

![reset](https://github.com/AdomasRep/Learning-Github/blob/main/Reset%20HEAD.png)

* Unfortunately, there is no quick way of going back more than one commit. However, there is a way to print all the commits done to the file. Each commit has a specific key. By copying this key, you can go back by more than one commit. The list of commits can be printed by: *git log*.

![log](https://github.com/AdomasRep/Learning-Github/blob/main/Log.png)

* By doing:  *git reset "commit key"*, you can see how things looked after that commit. 

![Reset to commit](https://github.com/AdomasRep/Learning-Github/blob/main/Reset%20to%20commit.png)

* If you want to delete all the changes after that commit simply do: *git reset --hard "commit key"*.

![Reset to commit hard](https://github.com/AdomasRep/Learning-Github/blob/main/Reset%20to%20commit%20hard.png)

## Forking 

Forking is used to create a copy of the repository. It does not make sense to fork your own repository. Therefore, usually someone else repository, which you do not have access to is forked. 
