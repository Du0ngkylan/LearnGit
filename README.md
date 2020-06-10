## LearnGit
Learn Git

-------------------
## Git Flow

### 1. Checkout
- `git clone http://.../.../front.git`

### 2. Init git flow  
- `git checkout master`
- `git flow init`

### 3.1. Create branch for develop new feature
- `git checkout develop`
- `git flow feature start WEBMART-FEATURE-SMS`
- `git branch`  
OR  
### 3.2. Create branch for fix bug
- `git flow bugfix start WEBMART-FIXBUG-355`
- `git branch`

### 4. Update source code
- `git status`
- `git add [list_file_changed]`

>>> 
Please carefully if you use below 'git add' command
>>> 

- `git add *`
- `git status`
- `git commit` ->Commit message should be format like this

>>>  
The 1st row:            [Credit Card] Write down detail content here  
The 2nd row:            [Do not fill anything, must be BLANK LINE]  
The 3rd row upper:      + Implement ABC feature  
                        + Correct properties file  
                        + Update XYZ procedure  
>>>  

OR
- `git commit -m "[Credit Card] Write down detail content here"`

### 5. Follow Coding Check List to update source code
TODO

### 6. Push source to origin
- `git push origin feature/WEBMART-FEATURE-SMS`

### 7. Get latest source code on DEVELOP branch and merge to current branch  
(ex: feature/WEBMART-FEATURE-SMS) by Rebase source code  

- `git pull --rebase origin develop`

### 8. Fix conflict if needed

- 1st case: In case of there are conflict files, please process like below  
>>> 
Step 1: fix all conflicted files  
Step 2:  
`git add *`  
Step 3: complete rebase process by below command  
`git rebase --continue`  
Step 4: after that, Push source code to current branch  
`git push -f origin feature/WEBMART-FEATURE-SMS`  
>>> 

- 2nd case: In case of there aren't any conflict file  
>>> 
`git push origin feature/WEBMART-FEATURE-SMS`
>>> 

### Create Merge Request (use GitLAB TOOL)
Please input the detail message and assign to Reviewer  
(Note: please inform to Reviewers as soon as by any channel :))  
In discussion box, please mark down #ISSUE_NO if have  

>>> 
Reviewers, after review source code, please check to checkbox "Remove source branch when merge request is accepted." in MERGE process
>>> 

>>> 
After your branch was merged, please deleted this branch on local and don't touch on in more and more  
`git branch -D feature/WEBMART-FEATURE-SMS`
>>> 

### Git Cheatsheet: (Help for you)
- `git status`
- `git fetch -p`
- `git branch`
- `git log --all --graph --decorate`
- `git checkout develop`
- `git branch -D feature/WEBMART-FEATURE-SMS`
- `git checkout feature/WEBMART-FEATURE-SMS`


### Add GIT remote [ TODO ]
- `git remote add fccl http://10.164.178.221:9999/TrainingGit/customer_release.git`
-> example: release source code to Customer's repository  

- `git remote -v` -> checkout remote list

### Release Flow [ TODO ]
- merge source from develop to master (accept merge request)  
- `git fetch -p` -> fetch lastest metadata from origin.
- `git checkout develop`
- `git pull origin develop`
- `git push fccl develop`
- `git checkout master`
- `git pull origin master` -> pull lastest source code.
- `git push fccl master`
- `git tag v{name}` -> create tag for release.
- `git push --tags` -> push tags to origin
- `git push --tags fccl`


