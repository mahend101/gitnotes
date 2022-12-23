# gitnotes
important commands using git. Minimalism is emphasized

Clone a repo
------------
git clone \<url\> <br>
cd \<dir\>  <br>
git pull

New Branch
-------------
git branch spielwiese/mahend (new branch)
git pull 
git branch --set-upstream origin spielwiese/mahend
git checkout spielwiese/mahend  (to change to already existing branch)

Commit:
---------
git commit -am "msg"
git push

Delete local branch
---------------------
link: https://www.git-tower.com/learn/git/faq/delete-local-branch/

git branch -d feature/showImageVersion
- but switch to another branch before deleting this 
- if remote is already pushed, then delete remote using 
	git push origin --delete <remote-branch-name>

force delete local -> git branch -D feature/showImageVersion

Merge:
----------
to merge hotfix to master
1. checkout to master
2. run merge with the branch name that the changes from this branch to be merged to master

git checkout master
git merge hotfix
git pull
git push

Example: Merge develop from remote to local branch features/msvcCompiler
git pull
git merge origin/develop
git push

:warning: Dont forget **git push** after Merge!!

After merge delete the hotfix branch
git branch -d hotfix

Merge RESET:
git merge --abort

Reset last commit 
----------------------
git reset --soft HEAD~1

Undo last Reset
---------
git reset 'HEAD@{1}'

Reset only one file from another commit
------------------------------------------
git checkout 5670de57 -- Project_BIN/Release/AppSystem.ini

where,  commit to take be applied (wished) = 5670de57 

## Show Last commit message

git log -1 

### Show last 2 commt messages 

git log -2

Deleted a file locally and didnt yet commit
-------------------------------------------
So you deleted a file, and immediately realized it was a mistake? This one is easy, just do: <br>
$ git checkout HEAD \<filename\>
