# Git tutorial
Git tutorial for beginners
## Intro
What is "version control" and why should you care? Have you ever copied a folder/file as a backup in case you end up messing the current one? Then at some point you actually mess both files? Well VCS will save you all the trouble.

VC is system that records changes to a file or set of files over time so that you can recall specific versions later. You can nearly version any type of file on a computer.

Being a developer, this tool is very important as it allows you to revert files back to previous state, revert the entire project back to a previous state, compare changes over time, log the changes and who applied them. Basically it is good if you screw things up, then you can easily recover. The VCS keeps a project history for retrieval.

Git is a VCS. It was released in 2005 and has matured since then. Follow the link below for more information about Git, its history and how it works.
https://git-scm.com/book/en/v2/Getting-Started-A-Short-History-of-Git

## Prerequisites
+ Install Git: to install it go to https://git-scm.com/book/en/v2/Getting-Started-Installing-Git and follow the instructions of your OS.
+ Have a github account: to create a new account, go to [GitHub page](https://github.com/)
+ Create a dir in your computer where you will put all the cloned repos: Since you are going to work on multiple projects, it is usually a good idea to create a new dir, eg /name_repos and clone all the git repos there.
+ Know the basics of how to use the terminal (eg: cd ls)

## Step 1: Clone the repo
A git repo stands for repository, which is simply a directory where all you project files will be located. In github, you can create as many public repositories as you want, generally one for each project you are working on.

As you might have noticed, this tutorial is contained in "git-tutorial" repo. All the changes you will make while following this tutorial will be contained in git-tutorial repo.

In order to make contribution to a project, you first have to clone the repo in your local device. Clonining means that all the content of the repo will be copied in your local device, so that you can run it or make changes. You can clone the git-tutorial repo as follows:

+ Go to: https://github.com/CodeClubAIU/git-tutorial. Here you can see all the files in in the repo.
+ Click the green button in the right "Clone or download". Copy the HTTPS link.
+ Open your terminal and cd to your /name_repos dir.
  * Run `git clone https://github.com/CodeClubAIU/git-tutorial.git`
  * A subdirectory named 'git-tutorial' should appear in your local drive.

## Step 2: Create a branch

This means you are duplicating the files. You may think of it as a way to request a brand new working directory, staging area, and project history that is an independent entity from the original branch (the parent) which is often called master locally and origin remotely.

To create a branch please go to : https://github.com/CodeClubAIU/git-tutorial
Click on Branch button type your branch name and click Create Branch, and your branch is created.

```
$ git fetch
$ git checkout < branch-name >
```

+ To check the status of your branch at anytime:

```
$ git status

```
## Step 3: Make a change to the local repo
Take some time to look at the files the local repo. By opening index.html in the browser (double click the file), you see a simple webpage containing a bunch of links. Clicking on those links will open some more webpages. In this tutorial you are going to modify this simple website, by adding your own link in index.html to your personal page.

+ Create a new .html file under/name_repos/git-tutorial named: < your-git-username >-profile.html For example: evis-e-profile.html
+ Write something interesting about yourself and save it.
+ Open your webpage in the browser to look at the result.
+ Once you are done editing the file and saved it, you will have wrap your changes in a commit, and then push in your branch. In the terminal type the following commands:
```
$ git add .
$ git commit -m "Insert message here"
$ git push origin < branch-name >
```

- 1st command is to add your files to git, which means you let git track the changes of the file. The '.' indicates that you want to add all files to be tracked. To only allow certain files to be tracked, you have to write the directory of these files. This is often called the staging area.
- 2nd command is to confirm the changes made in the added files and for them to be stored as a version of the project. (-m means you would like to add a message of the changes you made). This adds the staged snapshot to the history of your branch.
- 3rd command pushes your commit from the local to the <branch-name> in the remote repo.


+ Go to github and see your branch in the list of branches

Now that you have created your page, you can add a link to it in index.html:

+ Open index.html in a text editor, and modify the file as follows:
```
...
<h1>Git/Github tutorial</h1>
<p>This is the list of the awesome people who completed this tutorial:</p>

<p><a href="codeclub.html">CodeClub admin</a></p>
<p><a href="username-profile.html">Username's page</a></p>   <!-- Add this line -->
...
```

+ Next, again commit and push to your branch.

## Step 4: Make a pull request

+ The usual convention to have your branch merged (your changes appear in the main branch) with the main branch, is to create a pull request.
+ Pull requests is a feature to make collaborations easily with other developers. It is a mechanism to notify team members that they have completed a feature. Then the rest can review the code and merge it into the master branch, or comment on it if issues occur and discuss with the developer for further improvements. For more information you can read: https://www.atlassian.com/git/tutorials/making-a-pull-request/how-it-works

+ Go to the main page of the repository. In the "Branch" menu, choose the branch that contains your commits. To the right, click 'New pull request'

+ Use the base branch from the dropdown you'd like to merge your changes into (master) then choose your branch from the 'compare' branch drop-down. Type in a title and description (be concise and informative). Click 'Create pull request'.

https://help.github.com/articles/creating-a-pull-request/

## Step 5: Rebasing and merge conflicts

+ sometimes, other branches might have been updated and merged into the master. Thus the master branch now would have
a commit history ahead of the one present locally. In order to have a linear history of commits you have to follow:

+ Get the latest updates of master.

```
$ git checkout master
$ git pull
```

+ update your branch to incorporate the latest changes and create a linear history. You will use 'rebase' for that. Check the link below for information about rebasing.
https://git-scm.com/book/en/v2/Git-Branching-Rebasing

```
$ git checkout <branch-name>
$ git rebase -i master
```

+ after the last command. You will have the terminal opening a window with list of commits you have made. Like this:

```
 pick 034b3 'first commit message'
 pick 345df 'second commit message'
```

+ You will want to represent your branch with only one commit message. (p.s. the window is a vim and in order to use it, these are the commands list http://www.radford.edu/~mhtay/CPSC120/VIM_Editor_Commands.htm):
    * If you have more than one commit follow below:
        * press 'i' <!-- this changes the vim to allow you to input -->
        * change all the 'pick' apart from the 1st one to 'squash'. so it looks like this:
            ```
            pick 034b3 'first commit message'
            squash 345df 'second commit message'
            ```
    * press ESC then type ':wq!' <!-- this exits the input mode and saves the file -->
    * press enter

If you have successfully rebased then a message will appear that it was successful. Otherwise, seek a mentor for help.

* Unsuccessful rebasing can be due to the fact of merging issues. That is, if a file is changed in both your branch and the destination branch, and git doesn't know which version to keep then you will have to fix these conflicts manually then rebase again. <!-- Please ask the mentor to further explain if not understood -->
This link can demonstrate how to deal with conflicts: https://help.github.com/articles/resolving-a-merge-conflict-from-the-command-line/


## Resources:
https://www.atlassian.com/git/tutorials
