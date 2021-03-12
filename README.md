# Github Tutorial

I gotta learn Git and GitHub really fast!!

I deleted a line and then added a line!!

## Added This Subheading in VSCODE

I added this text after cloning the repo 
from github and opening in VSCODE.

## I used "ls -la" command show the hidden ".git" file that tracks changes to files in the GIT directory:

total 1
drwxr-xr-x 1 kinnp 197609   0 Mar 12 11:27 .
drwxr-xr-x 1 kinnp 197609   0 Mar 12 11:19 ..
drwxr-xr-x 1 kinnp 197609   0 Mar 12 11:33 .git
-rw-r--r-- 1 kinnp 197609   0 Mar 12 11:27 index.html
-rw-r--r-- 1 kinnp 197609 228 Mar 12 11:26 README.md

## I used "git status" to check for any changes to files that I'm tracking with git.

Git knows when I made a change to a file that GIT tracks and gave me this message:

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

## I created an index.html file and ran "git status" again: 

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html

## GIT told me the file was not being tracked.

I have to tell GIT that I want to track files before I can save it to GIT

## I can tell GIT which files or folders I want to add individualy with "git <file.name>"

## Or I can tell GIT to track all files in this folder with "git add ."

## Run "git status again":

$ git status
On branch main
Your branch is up to date with 'origin/main'.      

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md 
        new file:   index.html

## Now my files are ready to be committed using "git commit -m"

The FIRST -m option is for MESSAGE. This will be the TITLE of the message.

## Add a message to tell the reason for the commit: 

git commit -m "Updated Tutorial Repo"

## can also add a SECOND -m for the DESCRIPTION of the commit.

git commit -m "Updated Tutorial Repo" -m "I created an index.html file during my GIT tutorial and updated the README.md with what I learned during the lesson"

## <enter>

$ git commit -m "Updated Tutorial Repo" -m "I created an index.html file during my GIT tutorial and updated the README.md with what I learned during the lesson"
[main cf7795d] Updated Tutorial Repo
 2 files changed, 5 insertions(+)   
 create mode 100644 index.html  

(NOTE: After any changes to my files that have been saved, I must "git add ." to add changes to be committed and "git commit -m" to commit changes:)

$ git status
On branch main
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)   

nothing to commit, working tree clean

## This saves my commits locally, but their not live on GITHUB yet.

## I need to push them to GITHUB.









