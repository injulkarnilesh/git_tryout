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
alias gitspr='git stash && (git pull --rebase || echo "PULL FAILED") && git stash pop'
```

## Alias to pull all git repos (With stash)
```
alias gitpullall='workspace && find . -name ".git" -type d | sed "s/\/.git//" |  xargs -P2 -I{} sh -c "git -C {} stash && (git -C {} pull --rebase || echo "PULL FAILED") && git -C {} stash pop"'
```

## Git alias
```
alias.s status
alias.a !git add . && git status
alias.au !git add -u . && git status
alias.aa !git add . && git add -u . && git status
alias.c commit
alias.cm commit -m
alias.ca commit --amend
alias.ac !git add . && git commit
alias.acm !git add . && git commit -m
alias.l log --graph --all --pretty=format:'%C(yellow)%h%C(cyan)%d%Creset %s %C(white)- %an, %ar%Creset'
alias.ll log --stat --abbrev-commit
alias.lg log --color --graph --pretty=format:'%C(bold white)%h%Creset -%C(bold green)%d%Creset %s %C(bold green)(%cr)%Creset %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
alias.llg log --color --graph --pretty=format:'%C(bold white)%H %d%Creset%n%s%n%+b%C(bold blue)%an <%ae>%Creset %C(bold green)%cr (%ci)' --abbrev-commit
alias.d diff
alias.master checkout master
alias.spull svn rebase
alias.spush svn dcommit
alias.alias !git config --list | grep 'alias\.' | sed 's/alias\.\([^=]*\)=\(.*\)/\1\	 => \2/' | sort
alias.lg log --decorate --oneline
alias.st status
alias.pll pull --rebase
alias.psh push origin master
alias.dff diff --cached
```
