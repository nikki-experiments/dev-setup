# Gitconfig example file

If you don't have a .gitconfig file in your home directory create one:

  $ touch ~/.gitconfig
  
Use VI to open the file and add any aliases for git you'd like to use such as the following:

```
[alias]
        a = add
        b = branch
        cm = commit -m
        co = checkout
        cob = checkout -b
        d = diff
        p = push
        st = status
        rv = remote -v

        # one-line log
        l = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short

        # list branches sorted by last modified
        lb = "!git for-each-ref --sort='-authordate' --format='%(authordate)%09%(objectname:short)%09%(refname)' refs/heads | sed -e 's-refs/heads/--'"

        # list git aliases
        lg = "!git config -l | grep alias | cut -c 7-"
```
