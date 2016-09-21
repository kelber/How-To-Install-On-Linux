# Github commands

### Start project 

- From Github page
    + Create repository
    + Click in the "copy to clipboard" to copy the link repository
    + In command line 
```
git clone  (paste the link)
```

- From Command line <br>
    ``` 
        git init
    ```
    + make your project
    ```
        git remote add origin https://github.com/user/gitRepositoryName.git
        git remote -v
        git push -u origin master
    ```


#### Main commands and how contributed in remote repository

```
    git init
    git add .   --> git add all files or individual file:  git add FILE.txt
    git status  --> Check the status change
    git commit -m "Inicitial commit"
    git push origin master  --> push branch to github master branch
```


#### Checking status and commits <br>
```
    git status
    git log  --> see the commits
    git log --oneline  --> check the commits in oneline
```
Complete view <br>
```
    git log --oneline --decorate --all  --graph
```


#### Git Branch
    Use to input a new feature in the project

- Create a new Branch
    ```
        git branch feature1
        git checkout -b feature1    --> Check if exists the branch if not -b create the branch
    ```

- Change the branch or back to the master
    ```
        git checkout feature1
        git checkout master
    ```

#### Git Merge

    Use to update the master branch with the feature1 branch

- Go to master branch and do
    ```
        git checkout master
        git merge feature1
    ```
    
    It brings the feature1 files to master branch.  <br>
    Do it first to push the branch to master branch of github page.

- After merge the branch delete it
    ```
        git branch -D feature1
    ```

- Wanna create a new branch in the remote repository ?
    ```
        git push origin feature1
    ```
<br>

- Possible answers
    + 'fast-forward'  === Ok
    + 'Recursive' strategy  --> Diference between 2 branches and 1 commit, now have 2 parents 
        R. Make a new commit 

    + 'Conflit'
        Use to see the diff of the branchs
        ```
            git diff master origin/master
        ```
        
        ```
            git status .
            vim file.txt   --> Open the file with CONFLIT and delete the lines with conflit
            git add .
            git commit -m "commit"
            git branch -D feature2
        ```
- Other commands

    Bring files + Merge 
    ```
        git pull origin master
    ```
    Bring just files
    ```
        git fetch
    ```


    



#### Back to old commits <br>

```
git reset --soft  a4b1 (log number)
git reset --mixed a4b1  --> (untracked file)
git reset --hard  a4b1  --> avoid
```








