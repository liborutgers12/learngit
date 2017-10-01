Git is a version control system. Git is a free software.
This is a very simple tutorial of git and github.

Step 1: install git
	Linux: If it's not installed on the linux distribution you're using, install by
	$ sudo apt-get install git
	Windows: Download git windows version: http://msysgit.github.io/ and install and use git bash
	
	After installation, configure you name and email by
	$ git config --global user.name "Your Name"
	$ git config --global user.email "email@example.com"
	
Step 2: Create a local repository
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
Useful commands
	$ git status
	$ git diff filename
	$ git log
	$ git reset --hard HEAD^  // reset to the previous version; HEAD denotes the current version; ^,^^,^^ previous versions
	$ git reflog
	
	
	
	