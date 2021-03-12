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

## press enter

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

## Before committing to GIT, must generate a SSH KEY so Github will know Im the owner of the account

Use the following command:

ssh-keygen -t rsa -b 4096 -C "kinnpiano1970@gmail.com"

<press enter>
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/kinnp/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /c/Users/kinnp/.ssh/id_rsa
Your public key has been saved in /c/Users/kinnp/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:I0zMT3tydby5XG61Iv5KKJz1Xd5JOU54wyZHSvJ6ePs kinnpiano1970@gmail.com
The key's randomart image is:
+---[RSA 4096]----+
|                 |
|     o       .   |
|      + .  ...o. |
|     o o . .+.=o.|
|      o S.o  =o%o|
|      ..o=o +.@+B|
|       + . * =o=+|
|        . o + o. |
|           ooo.E |
+----[SHA256]-----+


## The key is saved in this directory:

/c/Users/kinnp/.ssh/id_rsa.pub

## There will be a PUBLIC KEY and a PRIVATE KEY

id_rsa.pub is the PUBLIC KEY

id_rsa is the PRIVATE KEY

## Keep the PRIVATE KEY SECRET ON MY LOCAL MACHINE!!!

## The PUBLIC KEY GOES ON GITHUB and gets compared to my PRIVATE KEY when I need to access GITHUB to prove my identity.

## Print PUBLIC KEY to screen and COPY IT. (switch to directoy with ssh keys)

$ cat id_rsa.pub

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDDBPpkQ5hC4ysZcaTiqoLfaykHdVaooNvtO8m9cAfHfImASUBPFPWJLkX6Tn5Qsc8AHS+0IKicFztQYTHEroRt0c4HFJWHLDgXqz8v0IT77O2xeBpNS4nDAP1vDKc0y9tylRbX9MjKJBqDoAtubqWFjeMwdxzKMO17uYkDzIRdz4R8jAEDVEw9bG7EZnifPjKxsmGwYBi/5p1tZCqP4gssDUpypYHt+n6fFk54XjJyBL1D62DrR9fyLZ+Em7X26vbxWcHCsrlgLibuhYuZj0JVvCoWkCJgHkm3udTZ+7kJ3EHTkQxUdCx1Ud6hoqnNDx6mN1ealtKwIgszJyVDa2Xv8eqYLrmXoVsxvHvRLQyjIFclh2OBCUbUbwHn7IoM10XUUI/4hlWmjUPH/KL19QeVRuGQlhfdt5np2jVnzLU2Zk5aDdSlWbd7zN99zIL7vEo19znLxjIvNu0Bt7SksSR47MG2g+Kln8bXLNFvPL4WzNUYgn1FpzS2g0KVDhhaPq+MIE/EolYEUAiIMGiiZEFFNjIXiQYveiiPhpa6ivqr9afoZcfbZLWnarqFMl86wSBd2W8+M0sUvNEPWF3t7Xid94eVHFzThgIglenmtUrec7q/yVb1frYLzkVpfJd5LPRmeU4irSbasGkLAWTSswtIcVaZL+PzOAEFTF6RQj80yQ== kinnpiano1970@gmail.com

## Goto "Settings>SSH and GPG keys>New SSH Key" in Github and give new key a title and paste in the PUBLIC KEY.

## Now I need to let the LOCAL CLI know about the new key I just created:
## Follow the steps below:

Adding your SSH key to the ssh-agent

Before adding a new SSH key to the ssh-agent to manage your keys, you should have checked for existing SSH keys and generated a new SSH key.

If you have GitHub Desktop installed, you can use it to clone repositories and not deal with SSH keys.

Ensure the ssh-agent is running. You can use the "Auto-launching the ssh-agent" instructions in "Working with SSH key passphrases", or start it manually:

## Start the ssh-agent in the background:

$ eval `ssh-agent -s`

## Gives you this response:

$ eval `ssh-agent -s`
Agent pid 1404

## Next: Add your SSH private key to the ssh-agent. 

If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_ed25519 in the command with the name of your private key file.

## Use the command below:

$ ssh-add /c/Users/kinnp/.ssh/id_rsa

## Gives you this:

$ ssh-add /c/Users/kinnp/.ssh/id_rsa
Identity added: /c/Users/kinnp/.ssh/id_rsa (kinnpiano1970@gmail.com)

Add the PUBLIC SSH key to your GitHub account.

## Use "git push" to push to GITHUB:

The tutorial said use: "git push orgin master"

I had to use "git push origin main" 

## The result:
(A popup came up and I had to login to GitHub and then press "authorize this machine" and  then it finally worked)

$ git push origin main
Logon failed, use ctrl+c to cancel basic credential prompt.
Enumerating objects: 22, done.
Counting objects: 100% (22/22), done.
Delta compression using up to 4 threads
Compressing objects: 100% (19/19), done.
Writing objects: 100% (20/20), 4.92 KiB | 315.00 KiB/s, done.
Total 20 (delta 5), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (5/5), done.
To https://github.com/kinnpiano1970/demo-repo.git
   2d7da30..732a2db  main -> main

## From the GitHub Page:

Success!
Authorization was successful. You will be redirected back to Visual Studio Code

Didn't work?
If you aren't redirected, you can add the token manually.

Your authorization token:
vscode://vscode.github-authentication/did-authenticate?windowid=1&code=91afb5e2a8b20dd4fd99&state=c6d33cf1-9e5b-45e1-a078-0f0563d4503e

✅ Copied
Copy the token.
Switch back to VS code.
Click Signing in to github.com... in the status bar.
Paste the token and hit enter.










