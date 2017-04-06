# Example config file for ssh config file

Add your configs changes to `~/.ssh/config`.

What I'm using right now:

[alias]
- st = status
- logrev = "log master.. --oneline --no-merges"
- co = checkout

[user]
- name = Nikki Purcell
- email = nichole.purcell@demandmedia.com

[color]
- ui = true

[push]
- default = simple
  
What I'd like to test out:

[alias]
  Show verbose output about tags, branches or remotes
- tags = tag -l
- branches = branch -a
- remotes = remote -v
Pretty log output
- hist = log --graph --pretty=format:'%Cred%h%Creset %s%C(yellow)%d%Creset %Cgreen(%cr)%Creset [%an]' --abbrev-commit --date=relative

[color]
Use colors in Git commands that are capable of colored output when outputting to the terminal
- ui = auto

[color "branch"]
- current = yellow reverse
- local = yellow
- remote = green

[color "diff"]
- meta = yellow bold
- frag = magenta bold
- old = red bold
- new = green bold

[color "status"]
- added = yellow
- changed = green
- untracked = cyan

Use `origin` as the default remote on the `master` branch in all cases
[branch "master"]
- remote = origin
- merge = refs/heads/master
