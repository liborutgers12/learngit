Git is a version control system. Git is a free software.
This is a very simple tutorial of git and github.
Summarized from https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000

# Step 1: install git
	Linux: If it's not installed on the linux distribution you're using, install by
	$ sudo apt-get install git
	Windows: Download git windows version: http://msysgit.github.io/ and install and use git bash
	
	After installation, configure you name and email by
	$ git config --global user.name "Your Name"
	$ git config --global user.email "email@example.com"
	
# Step 2: Create a local repository
	$ mkdir learngit
	$ cd learngit
	$ git init  
		Initialized empty Git repository in /Users/michael/learngit/.git/
	Create the files in the repo directory you'd like to add, e.g., readme.txt. Be caucious about the encoding method for windows: using UTF-8 without BOM
	$ git add readme.txt
	$ git commit -m "wrote a readme file"
		[master (root-commit) cb926e7] wrote a readme file
		1 file changed, 2 insertions(+)
		create mode 100644 readme.txt
# Useful commands
	$ git status
	$ git diff filename
	$ git log	// showing commit history
	$ git reset --hard commit_id //e.g. HEAD^  // reset to the previous version; HEAD denotes the current version; ^,^^,^^ previous versions
	$ git reflog // showing history with commit_id
	$ git checkout -- filename		
		// checkout filename in repo to workspace: discarding changes in workspace filename or restore deletion
	$ git reset HEAD readme.txt
		Unstaged changes after reset:
		M       readme.txt
	$ git rm test.txt
		rm 'test.txt'
	$ git commit -m "remove test.txt"

# Step 3: Remote Repo, on github.com
	a. Register an account if not yet.
	b. create SSH Key for the communicatoin between local and remote
		$ ssh-keygen -t rsa -C "youremail@example.com"
	c. create the empty remote repo on github
	d. push an existing repository from the command line
		$ git remote add origin https://github.com/liborutgers12/learngit.git
			//The remote repo are called "origin"
		$ git push -u origin master
			//-u for association for the first time; 
			//Branch master set up to track remote branch master from origin.
		$ git push origin master
			//no need for -u parameter
	e. clone from a remote repo
		$ git clone git@github.com:michaelliao/gitskills.git
		
# Branches: master and new branches
	branches are basically pointers
	$ git branch dev	//create new branch "dev"
	$ git checkout dev	//switch to "dev" from "master"
	$ git branch		//check existing and current branches
	revise/add files to "dev" and commit; 	
	switch back to master branch and merge dev to master, and delete branch "dev"
	$ git checkout master
	$ git merge dev
	$ git branch -d dev