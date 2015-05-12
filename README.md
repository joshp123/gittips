# gittips
how do you do the funky gibbon?

### HOW DO I ADD CHANGES?
`git add -p`

Always always always use git add -p to add your changes.
Never use `git add .`, if you do so you are literally worse than hitler and you're gonna regret it.

*Why?*


`git add .` adds everything in the entire directory to git.
This is super bad for many reasons - mainly because changes you haven't intended to include can sneak in. Commented code, debug lines, changes that don't work yet, etc. Even worse is untracked files, they are also included when you add the entire directory.


`git add -p` adds your changes interactively line by line. This is a thousand times better because you can see every single change you made, and decide whether you wish to add it.

If you wish to add an untracked file, specify the file exactly: `git add mynewfile.py -p`




git checkout (f)
git commit -v
git stash
git checkout -b "newbranch"

HOW DO I PUSH WITHOUT FUCKING UP DEVELOP
git push origin branchname

HELP I FUCKED UP WHAT DO
git reset --hard HEAD (^)
Whatever you do, DON'T PUSH, because then you change everyone elses branches too and have to revert stuff and it's generally awful.


I HAVE NO IDEA WHAT IN THE GODDAMNED HELL I AM DOING PLEASE HELP
read this all of this all of it then read it twenty more times and tattoo it on your arms
!!!! http://nvie.com/posts/a-successful-git-branching-model/ !!! 
