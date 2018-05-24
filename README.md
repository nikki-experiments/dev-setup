# My Dev Setup
This is my attempt at documenting my personal development setup on both my local Mac OS X and remote Linux VPS. My aim is to use the local computer for developing JavaScript applications and other coding experiments. The remote Linux server is where I manage my Wordpress blogs. I hope to update this project file when I upgrade or add programs or packages to my dev setups. I'll also list technologies that I'm interested in learning or using soon.

I've borrowed from other github repositories for some of this information.

- [Operating System](#operating-system)
- [Google Chrome](#google-chrome)
- [iTerm2](#iterm2)
- [Homebrew](#homebrew)
- [SSH](#ssh)
- [Git](#git)
- [Visual Studio Code](#visual-studio-code)
- [Project Folders](#project-folders)
- [Tech Stacks](#tech-stacks)
- [List of Programs](#list-of-programs)
- [Tools to Try Out](#tools-to-try-out)


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
I like to change terminal preferences to add color to help see what branch I'm on. Take the code from this [gist](https://gist.github.com/nikkipurcell/2f8c0cc81c008a1a3ef7a35d82de0f4f) and add it to your ~/.bash_profile file.

## Homebrew

I use Homebrew as a package manager for when I need to install programs on my Mac operating system. The process may change when I update my OS but as of (OS X Yosemite 10.10) you need to install **Command Line Tools** for **Xcode**. 
Read more about it [here](https://github.com/nikki-experiments/dev-setup/blob/master/homebrew.md).

Install **tree** using Homebrew to help you view directory structures. After installing just type tree to view the directory structure your in.

    $ brew install tree

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

## Git

Do your projects a favor by adding version control. [Git](https://git-scm.com/downloads) project repositories can be hosted in Github. Check to see if Git is already installed by running `$ git --version`. 
If not install it: 

    $ brew install git
    
Check the git version again to see if it installed correctly. Running `$ which git` should output `/usr/bin/git`.

Add basic git configurations that will be added to your `.gitconfig` file. You can also add aliases to your config file similar to the ones I use in this [.gitignore example file](https://github.com/nikki-experiments/dev-setup/blob/master/example-gitconfig.md).

You can also add to your global git config by using the following examples:

    $ git config --global user.name "Your Name Here"
    $ git config --global user.email "your_email@youremail.com"

It's a good idea to have a `.gitignore` file. Look at this boiler plate [example file](https://github.com/nikki-experiments/dev-setup/blob/master/example-gitignore.md).

Finally, here is a fun website that teaches the [basics of how to use git](http://rogerdudler.github.io/git-guide/).

## Visual Studio Code

As far as text editors go, I was a hardcore [Sublime Text](https://www.sublimetext.com/) user, then I used [Atom](https://atom.io/) and now I'm loving [Visual Studio Code](http://code.visualstudio.com/).

I love the embedded terminal, ease of installing packages, and debug features.

Some installed Packages I use: Babel ES6/ES7, ESLint, Flow Language Support, Prettier - Code formatter.

### Open Files In VSCode

Set up ability to open files in VSCode from the terminal: 
1. Launch VSCode
2. Type SHIFT+CMD+P then type 'shell command' .

3. Select **Shell Command: Install 'code' command in PATH** . 
4. Restart terminal for the new PATH value to take effect . 

Open files in VSCode from terminal window.
    
    $ code .

## Project Folders

I usually put my version controlled projects in `~/Projects`.
I usually put my non-version controlled experiments in [Codepen.io](https://codepen.io/).

## Tech Stacks

My coding projects mainly have been React JavaScript projects that use the following tools: 
  **Redux, Webpack, Babel, Prettier, Flow, React-Router, Gulp, Lodash Less, EsLint, Reselect, Redux-Devtools** and **Jest**.

I have used a few different tech stacks.
- JavaScript applications: **MERN** (MondoDB, Express, React, Node)
- Wordpress projects hosted on my VPS: **LAMP** (Linux, Apache, MariaDB, PHP)
- Local PHP development: **MAMP** (Apache, MySQL, PHP)

Variations to the stack choices above can include:
- NGINX for Apache
- Databases: mySQL, MariaDB, MongoDB, PostgreSQL
- Python for PHP


## List of Programs

These are some of the programs that I usually install on my new computers.

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

## List of Tools

These are either some of the tools that I use and others that I'd like to explore:

### Yarn

[Yarn](https://yarnpkg.com/en/) is a great package manager that installs packages for your projects. It's 100% deterministic, installs packages faster and has better caching than npm. Yarn locks down your dependencies by default (as opposed to npm shrinkwrap command which is more difficult to maintain). General rule is use Yarn for individual project installs and npm for library project installs or global installs where you may not want to lock down the dependencies.

To install it run `brew install yarn`.

To install a project's dependencies go to the project directory and run `yarn` (similar to npm install command). You'll see a list of dependencies being installed. A yarn.lock file will be created that automatically gets updated when you run yarn commands. If it's a new project with no dependencies yet run `yarn init` and answer the series of questions.

To add packages run `yarn add packagename`. 
A yarn.lock file will be created which locks down the exact dependencies to use on another machine. Don't modify this file.

Cool fact: you can run `yarn upgrade-interactive` to see all the packages for your project for which upgrades are available.

### Other programs include:

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
