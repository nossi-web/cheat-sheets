# git cheatsheet
========================================================================================

Remember, a typical workflow goes like this, 

code -> test -> code -> test -> code -> test REPO

Basic Repo workflow:
1) ADD modified files to the repo
2) COMMIT those files to memory with a message
3) PUSH those commits up to github.

Here's that Repo WorkFlow in CLI form
	$ git add -A
	$ git commit -m "your message here, what did you just do?"
	$ git push

remember, git status is your friend, and make sure you're in the directory where the repo is located. 
*hint* if you do a 
	$ ls -a
and list out the directory (folder) contents, you will see a 
	.git
directory at the top of the list.


COMMON GIT COMMANDS AND SYNOPSIS
=================================


Clone an existing repo from github to a local directory on your machine

	$ git clone

Initialize an empty git repository in the directory (folder) that you're in

	$ git init

Your friend! Tells you what is going on with git for the current directory

	$ git status

Add all the files and modified changes to existing files to the repository for tracking

	$ git add -A

Take a snapshot of the changes you've added to the repository
ALWAYS leave future you and other devs a message (-m)

	$ git commit -m "[your message here]"

Push the committed changes up to the repository on github

	$ git push

	$ git branch

	$ git checkout

Create a new branch for a feature based off of the dev branch

	$ git checkout -b MyFeature dev


When merging in a branch, remember that you'll probably have to checkout the branch first, pull changes from the repo on github, then checkout your working branch and then merge the changes. 

	$ git merge [branch-name]

Here's what that would look like, 
	
	$ git checkout dev
	$ git pull
	$ git checkout [your-branch]
	$ git merge dev -m "[message about branch merge]"


	
