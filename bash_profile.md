```
export PATH=/usr/local/bin:$PATH

[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*

function git-branch-name
{
    echo $(git symbolic-ref HEAD 2>/dev/null | awk -F/ {'print $NF'})
}

function git-dirty {
    st=$(git status 2>/dev/null | tail -n 1)
    if [[ $st != "nothing to commit (working directory clean)" ]]
    then
        echo "*"
    fi
}

function git-unpushed {
    brinfo=$(git branch -v | grep git-branch-name)
    if [[ $brinfo =~ ("[ahead "([[:digit:]]*)]) ]]
    then
        echo "(${BASH_REMATCH[2]})"
    fi
}

function gitify {
    status=$(git status 2>/dev/null | tail -n 1)
    if [[ $status == "" ]]
    then
        echo ""
    else
        echo "[$(git-branch-name)$(git-dirty)$(git-unpushed)]"
    fi
}

export PS1="\u@\w: \[\033[32m\]\$(gitify)\[\033[00m\] $ "
```
