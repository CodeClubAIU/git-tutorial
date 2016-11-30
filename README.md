# Git tutorial
Git tutorial for beginners
## Intro
Write about what is git, the importance of having a VCS 

## Prerequisites
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
  * A subdirectory named git-tutorial should appear in your local drive.

## Step 2: Create a branch
```
$ git branch < branch-name >
$ git checkout < branch-name >
```
## Step 3: Make a change to the local repo
Take some time to look at the files the local repo. By opening index.html in the browser, you see a simple webpage containing a bunch of links. Clicking on those links will open some more webpages. In this tutorial you are going to modify this simple website, by adding your own link in index.html to your personal page.

+ Create a new .html file under/name_repos/git-tutorial named: < your-git-username >-profile. For example: evis-e-profile.html
+ Write something interesting about yourself and save it.
+ Open your webpage in the browser to look at the result.
+ Once you are done editing the file and saved it, you will have wrap your changes in a commit, and then push in your branch:
```
$ git add .
$ git commit -m "Insert message here"
$ git push origin < branch-name >
```

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



TODO: merging issues


## Resources:
https://www.atlassian.com/git/tutorials

