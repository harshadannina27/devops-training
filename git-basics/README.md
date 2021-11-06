## Getting Started

### Installation
* Git
	```
	sudo apt install git
	```

### Configuration
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

