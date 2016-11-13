# Git tutorial
Git tutorial for beginners
## Intro
Write about what is git, the importance of having a VCS 

## Prerequisites
1. Have a git account
2. Create a dir in your computer where you will put all the cloned repos
3. Know the basics of how to use the terminal (eg: cd ls)

## Step 1: Clone the repo
1. Go: https://github.com/CodeClubAIU/git-tutorial
2. Click the green button in the right "Clone or download"
3. Copy the HTTPS link
4. Open your terminal and type git clone https://github.com/CodeClubAIU/git-tutorial.git
  * A subdirectory should appear in your local drive, with the same name as the repo you cloned.

## Step 2: Create a branch
```
$ git branch < branch-name >
$ git checkout < branch-name >
```
## Step 3: Make a change to the local repo
Take some time to look at the files the repo contains. Then make these changes:

1. Create a new .html file named: < your-git-username >-profile. For example: evis-e-profile.html
2. Edit that file, add facts about yourself.

Once you are done editing the file and saved it:
```
$ git add .
$ git commit -m "Insert message here"
$ git push origin < branch-name >
```
go to github and see your branch in the list of branches

## Step 4: Make a pull request



TODO: merging issues


## Resources:
https://www.atlassian.com/git/tutorials

