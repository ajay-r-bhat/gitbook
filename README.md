#Git Recipes

----------


##Git Basic Questions

 1. What is Git ?
 2. Why Git ?


##Basic Git Commands

 1. Change the last commit / Undo a commit, make a change and redo

    The last commit can be changed by the following commands
    ```git reset --soft HEAD~```

    ```git add <files>```

    ```git commit -c ORIG_HEAD```
    
 2. Undo a commit permanently
     
    ```git reset --hard HEAD~2```

    Last 2 commits i.e ```HEAD```, ```HEAD^```, ```HEAD^2``` are wrong and never want to look at them again. 
    Don't follow these steps if you have already shared the codebase on pushed to a remote repo where others can take
    a look. Look at questions with git-rebase in that case.
     
 3. Undo Commit, move it into a branch
    
    ```git branch topic/wip```

    ```git reset --hard HEAD~2```
    
    ```git checkout topic/wip```
    
    You made some commits, but realize its too early for them to exist in the master branch and want to continue perfecting
    them in the work-in-progress branch.
    
    So, we rewind the master and get rid of these commits and switch/checkout to the relevant branch and keep working.
    

 4. Reset an already added file
    
    ```git reset -- filename.extension```
    
    ```git commit -m "commit message"```

    ```git add filename.extension```
    
 5. Undo a merge/pull in a dirty working tree
    
    ```
       git pull

       Auto-merging <branch>
       
       Merge made by recursive.
       
        <branch>          | 10 ++++----
    
    ```
    
    ```git reset --merge ORIG_HEAD```
    
      
      After looking at merge, you may decide that the changes are not correct. Running ```git reset --hard HEAD``` will let
      
      you go back to HEAD, discarding your local changes. In order to keep the local changes you can just do
      
      ```git reset --merge ORIG_HEAD```
      
      
 6. A commit by 2 authors

		To add two authors for a single commit use the following commands
		
	  ```git --amend --reset-author```

 7. Add all files with a specific extension to git
 
    ```git add *.txt```

    This will add all ```.txt``` files to the git repository.
    
   Add all files from a specific subdirectory
   
   ```git add docs/*.txt```
   
 8. Remove files from git that have been deleted from filesystem.
    
    ```gir rm <file>.<extension>```

 9. Merge a branch called feature into current branch but do not make commits automatically
 
    ```git merge --no-commit feature```

    This is helpful when you want to include further changes to the merge. Tyically useful when bumping version/release numbers.
