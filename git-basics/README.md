## Getting Started 

### Installation
* Git
	```
	sudo apt install git
	```

### Configuration
* Cofigure username and email to track the author	
	```
	git config --global user.name "Harsha Dannina"
	git config --global user.email "harshadannina27@gmail.com"
	git config --list
	```

### Working on local Git repository
* Create folder
	```
	mkdir git_training_vi
	cd git_training_v1
	```
* Inintalize .git repository
	```
	git init
	```
* Basic git operations
	```
	touch first_file.txt
	git status
	git add .
	git status
	git commit -m "First file commit"
	git log
	git log --author="Harsha Dannina"
	git log --author="harshadannina27@gmail.com"
	```

## GitHub Setup

### Create GitHub account
* Sign-in to your github account and create a public repository eg: devops-training
	```
	git clone -b main https://github.com/username/devops-training.git
	cd devops-training
	```
* To pull the code from GitHub
	```
	git pull
	```

### Authenticate GitHub from git
1. Generate SSH Key
	```
	ssh-keygen -t ed25519 -C "your-github-mail@gmail.com"
	```
2. Add new SSH Key
	```
	cat ~/.ssh/id_ed25519.pub
	```
3. Copy the terminal output and paste in 
	* GitHub >  Settings > SSH and GPG keys > New SSH key
4. Test SSH connection
	```
	ssh -T git@github.com
	```
	Hi Username! You've successfully authenticated, but Github doesnot provide shell access.
5. If you clone the repo using HTTPS method, git push will prompt username and password everytime. So change it to SSH
	```
	git remote set-url origin git@github.com:username/repo-name.git
	```
6. Generate Personal Access Token(PAT)
	* GitHub > Settings > Developer settings > Personal access tokens > Generate new token > Fill the form > Generate token 

### Pushing code to GitHub
* Push code from local git to GitHub
	```
	touch testfile.txt
	git commit -a -m "Added testfile.txt"
	git push
	```
* It will ask credentials for first time. Give GitHub username and in password, give generated PAT token from the above step.

## Branching

### Creating sandpit branch
* Status of branch
	```
	git branch
	```
* Create new branch sandpit
	```
	git branch sandpit
	```
* Change current branch to sandpit
	```
	git switch sandpit
	```
* Add changes in sandpit
	```
	touch sandpit_file.txt
	git add .
	git commit -am "File added in sandpit"
	```
* Push file to sandpit branch
	```
	git push origin sandpit
	```
* Pull from sandpit branch
	```
	git pull origin sandpit
	```
### Merging sandpit with main branch
* Switch to main branch
	```
	git switch main
	```
* Merge sandpit into main branch
	```
	git merge sandpit
	```
* Push changes to GitHub
	```
	git add .
	git commit
	git push
	```
	
### Merging main with sandpit branch
* Switch to sandpit branch
	```
	git switch sandpit
	```
* Merge sandpit into main branch
	```
	git merge main
	```
* Push changes to GitHub
	```
	git add .
	git commit
	git push origin sandpit
	```

## Reset and Revert
* To review the logs and get commit ID
	```
	git log --oneline
	```
### Reset
* If the changes are local, and need to reset the last commit excluding the file changes
	```
	git reset --soft <commitID>
	git status
	```

* If changes are local, and need to reset the last commit including the file changes
	```
	git reset --hard <commitID>
	```

### Revert
* If the changes are pushed to GitHub repo, and needs to revert back to previous commit
	```
	git revert HEAD
	```
