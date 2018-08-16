# git_tryout
Trying out git with github


## Commands
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

$git diff --cached filename

$git log origin/master..HEAD //LOG UN-PUSHED

## Stash
$git stash list

$git stash save "Some stash message, goes to top of stash"

$git stash apply stash@{0} //does not remove

$git stash pop

$git stash drop stash@{1}

$git stash clear


## Alias to pull all git repos
```
alias gitpullall='workspace && find . -name ".git" -type d | sed "s/\/.git//" |  xargs -P5 -I{} git -C {} pull --rebase | grep "CONFLICT"'
```

## Git rebase pull with stash
```
alias gitspr='git stash && git pull --rebase || git stash pop'
```

## Alias to pull all git repos (With stash)
```
alias gitpullall='workspace && find . -name ".git" -type d | sed "s/\/.git//" |  xargs -P2 -I{} sh -c "git -C {} stash && git -C {} pull --rebase || git -C {} stash pop" | grep "CONFLICT"'
```