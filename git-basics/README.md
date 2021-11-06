## Getting Started with git

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

### Working on Local Git repository
* Create folder
	```
	mkdir git_training_vi
	cd git_training_v1
	```

* Inintalise .git repository
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

## Setting up GitHub 

### Create GitHub account
* Sign-in to your github account and create a public repository
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
5. If you clone the repo using HTTPS method, git push will prompet username and password everytime. So change it to SSH
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
