# case_study_git_workflow
This is the assignment for the case study for the git workflow

Question :
You work as a Devops Architect in Zendriix Softwares. The company has been struggling to manage their product releases. The releases should happen on 25th of every month. Suggest a Git Workflow Architecture for this requirement.
Simulate this workflow, by creating a pseudo code files and branches, and upload the same to your GitHub Account.

Solution : 
mkdir workflow
cd workflow/
sudo git init
Vijayas-MacBook-Air:workflow vijayasajwan$ ls -lrta
total 0
drwxr-xr-x+ 88 vijayasajwan  staff  2816 Oct  1 13:27 ..
drwxr-xr-x   3 vijayasajwan  staff    96 Oct  1 13:39 .
drwxr-xr-x  10 root          staff   320 Oct  1 13:39 .git
sh-3.2# pwd
/Users/vijayasajwan/workflow
sh-3.2# vi file.c
sh-3.2# git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	file.c

nothing added to commit but untracked files present (use "git add" to track)
sh-3.2# git add .
sh-3.2# git commit -m "initial code"
[master (root-commit) 45c282d] initial code
 Committer: System Administrator <root@Vijayas-MacBook-Air.local>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
 create mode 100644 file.c
sh-3.2# git branch feature1
sh-3.2# git branch feature2
sh-3.2# git branch
  feature1
  feature2
* master
sh-3.2# git branch develop
sh-3.2# git branch release

sh-3.2# git checkout feature1
Switched to branch 'feature1'
sh-3.2# vi 1.c
sh-3.2# git add .
sh-3.2# git commit -m "feature1 code added"
[feature1 222b126] feature1 code added
 Committer: System Administrator <root@Vijayas-MacBook-Air.local>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
 create mode 100644 1.c
sh-3.2# git status
On branch feature1
nothing to commit, working tree clean



sh-3.2# git checkout feature2
Switched to branch 'feature2'
sh-3.2# vi 2.c
sh-3.2# git add .
sh-3.2# git commit -m "feature2 code added"
[feature2 04d7a36] feature2 code added
 Committer: System Administrator <root@Vijayas-MacBook-Air.local>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
 create mode 100644 2.c
sh-3.2# git checkout develop
Switched to branch 'develop'
sh-3.2# ls
.git	file.c
sh-3.2# pwd
/Users/vijayasajwan/workflow

sh-3.2# cat file.c 
This is initial code


sh-3.2# git merge feature1
Updating 45c282d..222b126
Fast-forward
 1.c | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 1.c
sh-3.2# ls -lrt
total 16
-rw-r--r--   1 root  staff   21 Oct  1 13:40 file.c
-rw-r--r--   1 root  staff   16 Oct  1 15:18 1.c
drwxr-xr-x  14 root  staff  448 Oct  1 15:18 .git


sh-3.2# git merge feature2
Merge made by the 'recursive' strategy.
 2.c | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 2.c
sh-3.2# ls -lrt
total 24
-rw-r--r--   1 root  staff   21 Oct  1 13:40 file.c
-rw-r--r--   1 root  staff   16 Oct  1 15:18 1.c
-rw-r--r--   1 root  staff   15 Oct  1 15:23 2.c
drwxr-xr-x  14 root  staff  448 Oct  1 15:23 .git


sh-3.2# git checkout feature1
Switched to branch 'feature1'
sh-3.2# ls
.git	1.c	file.c
sh-3.2# vi 1.c
sh-3.2# cat 1.c
feature 1 added
error fixed
sh-3.2# git status
On branch feature1
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)
	modified:   1.c
no changes added to commit (use "git add" and/or "git commit -a")
sh-3.2# git add .
sh-3.2# git commit -m "feature1 error fixed"
[feature1 a8938db] feature1 error fixed
 1 file changed, 3 insertions(+), 1 deletion(-)
  
  sh-3.2# git checkout develop
Switched to branch 'develop'
sh-3.2# ls
.git	1.c	2.c	file.c
sh-3.2# cat 1.c
deature 1 added
sh-3.2# git merge feature1
Merge made by the 'recursive' strategy.
 1.c | 4 +++-
 1 file changed, 3 insertions(+), 1 deletion(-)
sh-3.2# cat 1.c
feature 1 added
error fixed

git checkout release
git merge develop
git checkout master
git merge release
ls
git remote add origin "Repo URL"
git push origin master

POST RELEASE :
==============
sh-3.2# git branch hotfix
sh-3.2# git branch
  develop
  feature1
  feature2
  hotfix
* master
  release
sh-3.2# git checkout hotfix
Switched to branch 'hotfix'
sh-3.2# ls
.git		1.c		2.c		README.md	file.c
sh-3.2# vi 2.c
sh-3.2# git status
On branch hotfix
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   2.c

no changes added to commit (use "git add" and/or "git commit -a")
sh-3.2# git add .
sh-3.2# git commit -m "hotfix"
[hotfix e13f62f] hotfix
 1 file changed, 1 insertion(+)
sh-3.2# cat 2.c
feature2 added
error resolved
sh-3.2# git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
sh-3.2# git brach
git: 'brach' is not a git command. See 'git --help'.

The most similar command is
	branch
sh-3.2# git branch
  develop
  feature1
  feature2
  hotfix
* master
  release
sh-3.2# git checkout master
Already on 'master'
Your branch is up to date with 'origin/master'.
sh-3.2# git merge hotfix
Updating 06ee744..e13f62f
Fast-forward
 2.c | 1 +
 1 file changed, 1 insertion(+)
sh-3.2# cat 2.c
feature2 added
error resolved
sh-3.2# git push orgin master
fatal: 'orgin' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
sh-3.2# git push origin master
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 283 bytes | 283.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/vijayasajwan0810/case_study_git_workflow.git
   06ee744..e13f62f  master -> master



