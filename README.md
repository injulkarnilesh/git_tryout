# git_tryout
Trying out git with github
It's cool!

## Wow
Change from local repo diff file.

We changed the file and line same. Yeah!

$git status

$git pull --rebase origin master

$git status

$git diff

$git add README.md

$git diff --cached

$git commit -m 'commit message'

$git diff COMMIT1 COMMIT2 README.md

$git origin master

$git pull --rebase origin master

$git add README.md //to mark file resolved

$git rebase --continue  //after same line conflict resolution

$git push origin master

$git log --decorate --oneline

$git diff HEAD filename

$git mergetool

$git diff origin/master..HEAD //DIFF UN-PUSHED

$git log origin/master..HEAD //LOG UN-PUSHED

Alias to pull all git repos from workspace :
alias gitpullall='workspace && find . -name ".git" -type d | sed "s/\/.git//" |  xargs -P5 -I{} git -C {} pull --rebase | grep "CONFLICT"'
