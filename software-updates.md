# Keep Your Software Organized and Up To Date
This document will help me to remember what software I have and what needs to be updated.

### Operating System
Make sure the operating system software is updated.

| Item     | Frequency | How To Update Item           |
|----------|-----------|------------------------------|
| Mac OS X | Weekly    | Apple Icon > Software Update |
| Homebrew | Weekly    | Run: brew update             |

### Software Packages Intalled by Homebrew
Every so often check the software that you've installed with homebrew and keep up to date as needed.

- `brew list` to see what was installed using homebrew.
- `brew outdated` to check which packages are out of date.
- `brew upgrade packagename` to upgrade specific packages.
- `brew pin packagename` if you don't want to update specific packages. 
- `brew uninstall packagename` to uninstall software.

### Node.js
You don't have to update node unless maybe your working on a new project and want to start with the latest stable version of Node.
Use `nvm` to manage different versions of Node on your server.

- `nvm ls` to list out all the installed versions of node.
- `nvm use 4.2.1` if you wanted to switch to node version 4.2.1.
- `nvm uninstall 0.10` to uninstall an older version of node you no longer need.

### NPM
NPM updates more often than node so you definitely want to make sure this is updated more often.

- `npm install npm@latest -g` to update to the latest version of npm.

### Git
This is one of the projects that was probably installed on the Mac by using Homebrew. So use Homebrew to update it.
If you want to see if your version of git is a security threat go to this [page](https://confluence.atlassian.com/bitbucketserver/installing-and-upgrading-git-776640906.html). 
Also you can see if your version of git is out of date by first running `git --version` to check the version and then looking on the [Bitbucket Server supported platforms](https://confluence.atlassian.com/bitbucketserver/supported-platforms-776640981.html) page.
