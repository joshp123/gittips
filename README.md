# gittips
how do you do the funky gibbon?

### How do I add changes?
`git add -p`

Always always always use git add -p to add your changes.
Never use `git add .`, if you do so you are literally worse than hitler and you're gonna regret it.

*Why?*


`git add .` adds everything in the entire directory to git.
This is super bad for many reasons - mainly because changes you haven't intended to include can sneak in. Commented code, debug lines, changes that don't work yet, etc. Even worse is untracked files, they are also included when you add the entire directory.


`git add -p` adds your changes interactively line by line. This is a thousand times better because you can see every single change you made, and decide whether you wish to add it.

If you wish to add an untracked file, specify the file exactly: `git add mynewfile.py -p`

### How do I commit like a pro?

`git commit -v` 

Use this and ONLY this. (No `git commit -a` bullshit that is as terrible as `git add .`)

The `-v` flag means verbose, and this prints out a full summary of the commit below where you enter the commit message. This is super useful because you get another chance to review it (first when you write the code, second when you stage the changes line by line using `git add -p`), and you can catch any embarassing mistakes.

This is *especially* important for merge commits, so that you can check that no merge conflicts have snuck in. If you manage to commit a merge conflict we will laugh at you forever.

### How do I switch branches or get rid of something?

`git checkout branch` to switch branches. 

`git checkout` to reset your changes in a branch, for example if you had some bad 

Add the `-f` flag to force a checkout, for example to discard changes when switching between branches.

### How do I make a new branch?

`git checkout -b "newbranch"`


### If you have made some changes and aren't ready to commit them yet:
`git stash save "describe your changes"` to save

`git stash pop` to apply the last stashed changes

`git stash show` and `git stash apply {1}` to apply a specific stashed change.


### How do I merge changes properly?
`git fetch && git merge --no-commit --no-ff -s recursive -X patience -X ignore-space-change origin/develop` 

This fetches changes and then merges the branch origin/develop in to your local branch. You then need to commit to finish the merge. ALWAYS ALWAYS ALWAYS fix merge conflicts first if there are any. 


### How do I push without fucking up other branches?
`git push origin branchname`.

This pushes ONLY the specified branch, which means if you were an idiot and commited to develop, then nobody will ever know, because you didn't push there. If you use `git push` it pushes all branches you have locally which is bad.

## HELP I FUCKED UP WHAT DO
`git reset --hard HEAD` to reset your changes to the last commit

`git reset --hard HEAD^` to reset your changes to the *previous* commit (if, for example, you accidentally commited to develop and want to revert that commit). Add more `^`s to go back futher.

Whatever you do, DON'T PUSH, because then you change everyone elses branches too and have to revert stuff and it's generally awful.


## I HAVE NO IDEA WHAT IN THE GODDAMNED HELL I AM DOING PLEASE HELP
read this all of this all of it then read it twenty more times and tattoo it on your arms
!!!! http://nvie.com/posts/a-successful-git-branching-model/ !!! 
