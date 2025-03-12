For the first time user: 
git config --global user.name “Your Name” Set the name that will be attached to your commits and tags.
git config --global user.email “you@example.com”
Set the e-mail address that will be attached to your commits and tags. 
References: GitLab https://about.gitlab.com/images/press/git-cheat-sheet.pdf


Working a project
Clone a repository: git clone <repo_name>
Make some changes to the README file
Add file to staging area: git add <filename>
Commit to Local Repository: git commit -m "<message>"
Push to Remote Repository: git push origin <branch_name>
Changes something in the readme file from the GitHub Repo
Pull from the Local Working Directory: git pull origin <branch_name>
View Logs: git log

Creating a Branch:
Creating a Branch from GitHub:
Go to Remote Repo and create a branch

Creating a Branch Using Command Lines:
List all local branches in repository. With -a: show all branches (with remote): 
Create new branch, referencing the current HEAD: git branch [branch_name] 
