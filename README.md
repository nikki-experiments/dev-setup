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

When I'm not using the terminal in my code editor I can use iTerm to make changes on my operating system. This is helpful when installing or deleting programs. Download and install [iTerm2](http://www.iterm2.com/) for a better terminal experience.
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
 
Generate an SSH key so you can distribute. I originally used the code below but for more step by step instructions, [atlassian has a great tutorial](https://support.atlassian.com/bitbucket-cloud/docs/set-up-an-ssh-key/#SetupanSSHkey-ssh2) on generating public and private SSH keys.
 
    $ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   
Accept the default location to save the key. You will be prompted to type a secure passphrase. Good idea for safety.

## Git

Do your projects a favor by adding version control. [Git](https://git-scm.com/downloads) project repositories can be hosted in Github. Check to see if Git is already installed by running `$ git --version`.

### Installing Git

To install Git use homebrew:

    $ brew install git

Check the git version again to see if it installed correctly. Running `$ which git` should output `/usr/bin/git`.

### Configuring Git

After installing Git, you should have a `.gitconfig` file in your home directory (cd ~). This is where you will add all git configurations.

#### Add global configs

Git will need your username and email to be set as a global configuration. Type this in your terminal:

    $ git config --global user.name "Your Name Here"
    $ git config --global user.email "your_email@youremail.com"

#### Set aliases

 Next you should create aliases (shortcuts) for your git commands to allow you to be more efficient while you develop.
 Use the [.giticonfig example file](https://github.com/nikki-experiments/dev-setup/blob/master/example-gitconfig.md) to set these.

    $ cd ~
    $ vi .gitconfig
    // Make changes to config file
    // Save changes in vi :wq!

### Create .gitignore file

It's a good idea to have a `.gitignore` file. Look at this boiler plate [gitignore example file](https://github.com/nikki-experiments/dev-setup/blob/master/example-gitignore.md).

Of course, look up the lastest documentation to know how best to use Git. This website teaches the [basics of how to use git](http://rogerdudler.github.io/git-guide/).

## Visual Studio Code

[Visual Studio Code](http://code.visualstudio.com/) is the most popular lightweight cross-platform editor.

### Configuration

Some **VS extensions** I've enabled in VSCode include: Auto Close Tag, Auto Complete Tag, Auto Rename Tag, Emoji, Error Lens, ESLint, GitLens - Git supercharged, Live Server, Markdown Preview Enhanced, Path Intellisense, Prettier - Code formatter, Simple React Snippets, TODO Highlight, Version Lens, vscode-styled-components. 

A few extensions I might not use since I will include them in the project using npm. These include ESLint.

After you install the **Prettier** extention (called Prettier - Code Formatter) open the VScode Settings file and search for 'default formatter'. Then select esbenp.prettier-vscode. Then search for 'format onSave' and make sure it is checked. If your project is not using a specific npm Prettier package then the default VScode extension will be used to format your pages. Otherwise the npm package should take presedence. You can always disable the extension if you get conflicting Prettier rules.


Set **VS settings** in VS Code: Shift + CMD + P.
Then choose Preferences: Open Settings (JSON). 
Below is my most recent object settings.

```
// place settings here to override default settings
{
  "editor.accessibilitySupport": "off",
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "editor.insertSpaces": true,
  "editor.linkedEditing": true,
  "editor.multiCursorModifier": "ctrlCmd",
  "editor.renderWhitespace": "all",
  "editor.renderControlCharacters": true,
  "editor.tabSize": 2,
  "editor.wordWrap": "on",
  "files.autoSave": "onFocusChange",
  "files.insertFinalNewline": true,
  "files.trimFinalNewlines": true,
  "files.trimTrailingWhitespace": true,
  "javascript.updateImportsOnFileMove.enabled": "always",
  "liveServer.settings.donotShowInfoMsg": true,
  "search.exclude": {
    "**/node_modules": true,
    "**/bower_components": true,
    "**/.out": true,
    "**/.vscode": true,
    "**/.tmp": true
  },
  "terminal.integrated.shell.osx": "/bin/bash",
  "todohighlight.isCaseSensitive": true,
  "todohighlight.keywords": [
    {
      "text": "TODO",
      "color": "#333",
      "backgroundColor": "#2ecc71"
    }
  ],
  "typescript.updateImportsOnFileMove.enabled": "always",
  "versionlens.suggestions.showOnStartup": true,
  "window.zoomLevel": 1,
  "workbench.colorTheme": "Ayu One",
  "workbench.iconTheme": "Monokai Pro Icons"
}
```

**VS Color Theme**: Code -> Preferences -> Color Theme
Choose one of the previously installed or install a new one. Using Ayu Mirage PowerUp, Ayu Adaptive, and Monokai Pro.

**VS Icon Theme**: Code -> Preferences -> File Icon Theme
Choose one of the previously installed or install a new one. Using Monokai Pro Icons today after installing Monokai Pro.

**VS Code Terminal Format**: 
Use this article to help customize your VS Code Terminal format. I use 1)username 2)space 3)directory 4)space 5)git branch 6)space 7)end character $. (Customize Your VS Code Terminal)[https://medium.com/@charlesdobson/how-to-customize-your-macos-terminal-7cce5823006e]. To set each item to the color that you like use this article: (How to colorize your bash prompt)[https://www.howtogeek.com/307701/how-to-customize-and-colorize-your-bash-prompt/].

### Set Global Code Snippets

You can set up commonly used snippets w/in VScode such as console.log(); so you don't have to type each type. To do this go to VScode -> Preferences -> User Snippets. Choose new global snippets file. Give name common. Then uncomment the console.log example and change prefix to 'cl' and remove the $1 and $2 variables in the code. Save. Test by going to your code and type 'cl' then TAB to autocomplete the console command.

### Install Live Server

When using VS Code, you can use Live Server (a lightweight web server) to serve your JavaScript application. Add and install it in your VS Code extensions. Restart VS Code for it to take effect.

To use it, simply right click on your index.html file and choose Open with Live Server in the dropdown. This will open a browser and point to the address where your web application will be served from.

React applications have their own web server setup so you wont need to use Live Server for those projects. 

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
The main front-end tech stack I use is **React** to render the UI and **Node.js** to use npm to install and manage 3rd party packages.
For the backend I've used Express to help build apis. In the future I will have exposure to popular backend tools like GraphQL, Apollo, Python and possibly Rails.

Tech stacks I've worked with in the past include:
- JavaScript applications: **MERN** (MondoDB, Express, React, Node)
- Wordpress projects hosted on my VPS: **LAMP** (Linux, Apache, MariaDB, PHP)
- Local PHP development: **MAMP** (Apache, MySQL, PHP)

Variations to the stack choices above can include:
- NGINX for Apache
- Databases: mySQL, MariaDB, MongoDB, PostgreSQL
- Python for PHP


## List of Programs

These are some of the other programs that I usually install on my new computers.

- Lastpass - stores all passwords
- Evernote - best note taking app with the biggest muscles
- Photoshop - for design
- Sequel Pro - free GUI for mySQL databases
- Postman - program for testing api requests
- Alfred - tool for searching Mac applications
- Microsoft Office - Word, Excel, Powerpoint
- Pulse Secure - used to connect to corporate resources using VPN.

## List of Tools

These are either some of the tools that I use and others that I'd like to explore:

- Github - host public and private Git repositories, keep track of revisions and collaborations.
- Slack - communication app 
- OneDrive - cloud storage for sharable documentation, photos, other files (Microsoft) - popular across enterprise organizations.
- Google Drive - cloud storage for documentation, photos, other files (free for 5GB)
- Dropbox - free for 2GB good for backup.

Review my [SEO tools file](https://github.com/nikki-experiments/dev-setup/blob/master/seo.md).


### Helpful tools to explore:

- [Spectacle](https://www.spectacleapp.com/) - move and resize windows free 


### Fullstack technologies to explore:

- Elasticsearch - open source, real-time search and analytics engine (runs on Java)
- Redis - key-value store similar to NoSQL database. Can be used for session management or caching by web apps
- Python - review article (http://blog.teamtreehouse.com/what-is-python)
- Heroku - Platform as a Service (PaaS) - deploy apps online
- ComodoSSL - Encryption (TLS/SSL) this protocol increases the security of data transmitted thorugh the internet. Free option called **Let's Encrypt!**
- Cloudflare - Content Delivery Network (CDN) that is fast and free to implement. Just point your name servers to Cloudflare's for lower bandwidth usage. Sites should get speed and performance boost!
- mySQL Workbench - mySQL database management
- VirtualBox - virtual machine management
- Vagrant
- Docker - container management
- composeEnhancers

