#Git Recipes

----------


##Git Basic Questions

 1. What is Git ?
 2. Why Git ?


##Basic Git Commands

 1. Change the last commit / Undo a commit, make a change and redo

    The last commit can be changed by the following commands
    ```git reset --soft HEAD^```

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
    

 2. A commit by 2 authors

		To add two authors for a single commit use the following commands

