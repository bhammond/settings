```
[core]
    repositoryformatversion = 0
    filemode = true
    bare = false
    logallrefupdates = false
    ignorecase = true
    precomposeunicode = false
[remote "origin"]
    url = git@github.com:TruHearing/t3.git
    fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
    remote = origin
    merge = refs/heads/master
[help]
    autocorrect = 1
[user]
    email = bretthammond@stubthumb.com
    name = Brett Hammond
[apply]
    whitespace = nowarn
[merge]
    summary = true
[push]
    default = current
[remote "origin"]
    push = HEAD
[diff]
    ignoresubmodules = untracked
[alias]
    aliases = config --get-regexp ^alias\\.
    a  = add
    c = commit
    co = checkout
    bn = checkout -b
    ma = checkout master
    b  = branch
    br = branch
    ls = branch
    bt = branch --track
    ba = branch -a
    bd = branch -d
    s  = status
    st = status
    w = whatchanged
[color]
    ui = auto
    branch = auto
    diff = auto
    status = auto
[color "branch"]
    current = yellow reverse
    local = yellow
    remote = green
[color "diff"]
    meta = yellow bold
    frag = magenta bold
    old = red bold
    new = green bold
[color "status"]
    added = yellow
    changed = green
    untracked = cyan
```
