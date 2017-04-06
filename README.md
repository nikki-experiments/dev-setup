# My Dev Setup
This is my attempt at documenting my personal development setup on both my local Mac OS X and remote Linux VPS. My aim is to use the local computer for developing JavaScript applications and other coding experiments. The remote Linux server is where I manage my Wordpress blogs. I hope to update this project file when I upgrade or add programs or packages to my dev setups. I'll also list technologies that I'm interested in learning or using soon.

I've borrowed from other github repositories for some of this information.

- [Operating System](#operating-system)
- [Google Chrome](#google-chrome)
- [iTerm2](#iterm2)
- [Atom](#atom)
- [Homebrew](#homebrew)
- [Git](#git)
- [Tech Stacks](#tech-stacks)
- [SSH](#ssh)
- [List of Programs](#list-of-programs)
- [Tools to Try Out](#tools-to-try-out)
- [Project Folders](#project-folders)

## Operating System

The operating system I use for my desktop and laptop computer is **Mac OS X**.
The operating system I use for my Virtual Private Server (VPS) is **Linux**.

### System updates

Before installing anything, make sure the operating system is updated to the latest version.
- For MAC: **Apple Icon > Software Update...**
- For Linux: Visit the official linux kernal website to determine what the current stable version of the kernal is. (More to come).

### System preferences

These are security settings I usually put on my computer (especially the laptop). Under **System Preferences > Security & Privacy** set the following:
- General: Add password when computer sleeps or screen saver begins
- Firewall: Turn Firewall On
- FileVault: Turn on. Disk encryption system that protects against physical access to your computer. (Must remember recovery key and password or data will be lost).

Look into: Time Machine to backup data on your computer.

## Google Chrome

Install your favorite browser, mine happens to be [Google Chrome](https://www.google.com/intl/en/chrome/browser/).
It's a good idea to use all browsers so you test your pages on all of them.

Options include: [Firefox](https://www.mozilla.org/en-US/firefox/products/), [Opera](http://www.opera.com/), [Safari(Mac only)](http://www.apple.com/safari/), [Edge(Windows only)](https://www.microsoft.com/en-us/windows/microsoft-edge)

## iTerm2

Download and install [iTerm2](http://www.iterm2.com/) for a better terminal experience.
I like to change terminal preferences to add color and to see what branch I'm on. Take the code from this [gist](https://gist.github.com/nikkipurcell/2f8c0cc81c008a1a3ef7a35d82de0f4f) and add it to your ~/.bash_profile file.

## Atom

As far as text editors go, I was a hardcore Sublime Text user, until I discovered Atom. There are lots of reasons why I switched to Atom. For starters I love how easy it is to install packages and themes. Sublime was lightning fast and if Atom catches up I don't think I'll be going back to Sublime (but we had a great run)! [Atom](https://atom.io/) is currently my favorite text editor.

Other text editors: [Sublime Text](https://www.sublimetext.com/), [Visual Studio Code](http://code.visualstudio.com/), [Brackets](http://brackets.io/) 

## Homebrew

I use Homebrew as a package manager for when I need to install programs on my Mac operating system. The process may change when I update my OS but as of (OS X Yosemite 10.10) you need to install **Command Line Tools** for **Xcode**. 

### Install
I already had Xcode installed on my machine. I just needed to install the Command Line Tools. (Note: Newer OS X versions will no longer require you to download CLT or Xcode for this step).

    $ xcode-select --install
  
To check the command line tools version run this:

    $ xcode-select --version
  
Now install Homebrew:

    $ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  
You should run the following command to make sure there are no issues you need to correct with Homebrew:

    $ brew doctor

### Usage

It is high time I give credit to the excellent mac-dev-setup instructions of [nicholashery](https://github.com/nicolashery/mac-dev-setup). I will refer you to his page to read up on how to use Homebrew to install packages.

## Git

Do your projects a favor by adding version control. [Git](https://git-scm.com/downloads) project repositories can be hosted in Github. Check to see if Git is already installed by running `$ git --version`. 
If not install it: 

    $ brew install git
    
Check the git version again to see if it installed correctly. Running `$ which git` should output `/usr/bin/git`.

Add basic git configurations that will be added to your `.gitconfig` file. You can also add aliases to your config file similar to the ones I use in the example file. (TODO: add example file)

    $ git config --global user.name "Your Name Here"
    $ git config --global user.email "your_email@youremail.com"

Also create a `.gitignore` file. Look at the example file. (TODO: add example file)
Here is a fun website that teaches the [basics of how to use git](http://rogerdudler.github.io/git-guide/).

## Tech Stacks

I have a few different tech stacks that I use.
- Wordpress projects hosted on my VPS: **LAMP** (Linux, Apache, MariaDB, PHP)
- Local PHP development: **MAMP** (Apache, MySQL, PHP)
- JavaScript applications: **MERN** (MondoDB, Express, React, Node)

Variations to the stack choices above can include:
- NGINX for Apache
- Databases: mySQL, MariaDB, MongoDB, PostgreSQL
- Python for PHP

### ReactJS

So far my favorite Javascript Framework is [React](https://facebook.github.io/react/). I won't list them all but some of the modules I use with React projects include **react-router, babel, gulp, lodash, less, webpack, eslint, redux, reselect,** and **redux-devtools**.

### NodeJS

So 

### CSS Preprocessor

I started using [LESS](http://lesscss.org/) so it's what I'm most familiar with but [SASS](http://sass-lang.com/) is also very popular. I'd like to learn that soon.

## SSH

I use **Secure Shell (SSH)** to connect to remote hosts via the command line. To make it easier to login, create a config file at `~/.ssh/config`.

    Host example,
        Hostname example.com
        User user.name
 
 This creates an alias for `user.name@example.com`. To run the alias type `ssh example` in terminal.
 
 ### Generate SSH key
 
Generate an SSH key so you can distribute.
 
    $ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   
Accept the default location to save the key. You will be prompted to type a secure passphrase. Good idea for safety.

## List of Programs

These are some of the programs that I usually install on my computer.

- Dropbox - free for 2GB good for backup.
- Google Drive - similar, good for docs (free for 5GB)
- Lastpass - stores all passwords
- Evernote - best note taking app with the biggest muscles
- Google Keep - nice simple note taking that can be accessed offline.
- Photoshop - for design
- Gimp - free photoshop alternative
- Sequel Pro - free GUI for mySQL databases
- Slack - communication app 
- Numbers - Apple equiv of Excel
- Pages - Apple equiv of Word
- Github - host public and private Git repositories, keep track of revisions and collaborations.
- Wordpress - Content Management System (CMS) of choice. Unfortunately not very secure. Alternative CMS: Jekyll. Review my [SEO tools file](https://github.com/nikki-experiments/dev-setup/blob/master/seo.md).

## Tools to try Out

These are the other tools that I might or might not have used but would like to explore more:
- Yarn - alternate package manager
- [Spectacle](https://www.spectacleapp.com/) - move and resize windows free 
- Primitive - A CSS framework that provides a base stylesheet
- Gulp - Task runner that provides compiling, minifying, autoprefixing, linting, and more. Use globally (npm used for local projects)
  Another option is Grunt.
- Elasticsearch - open source, real-time search and analytics engine (runs on Java)
- Redis - key-value store similar to NoSQL database. Can be used for session management or caching by web apps
- Python - review article (http://blog.teamtreehouse.com/what-is-python)
- Heroku - Platform as a Service (PaaS) - deploy apps online
- ComodoSSL - Encryption (TLS/SSL) this protocol increases the security of data transmitted thorugh the internet. You must pay but there is a free option called **Let's Encrypt!**
- Cloudflare - Content Delivery Network (CDN) that is fast and free to implement. Just point your name servers to Cloudflare's for lower bandwidth usage. Sites should get speed and performance boost!
- VirtualBox - virtual machine management
- Vagrant
- Docker - container management
- composeEnhancers
- mySQL Workbench - mySQL database management

## Project Folders

I usually put my version controlled projects in `~/Projects`.
I usually put my non-version controlled projects in `~/Dropbox`.
