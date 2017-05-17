# My Dev Setup
This is my attempt at documenting my personal development setup on both my local Mac OS X and remote Linux VPS. My aim is to use the local computer for developing JavaScript applications and other coding experiments. The remote Linux server is where I manage my Wordpress blogs. I hope to update this project file when I upgrade or add programs or packages to my dev setups. I'll also list technologies that I'm interested in learning or using soon.

I've borrowed from other github repositories for some of this information.

- [Operating System](#operating-system)
- [Google Chrome](#google-chrome)
- [iTerm2](#iterm2)
- [Atom](#atom)
- [Homebrew](#homebrew)
- [SSH](#ssh)
- [Git](#git)
- [LESS](#less)
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
I like to change terminal preferences to add color and to see what branch I'm on. Take the code from this [gist](https://gist.github.com/nikkipurcell/2f8c0cc81c008a1a3ef7a35d82de0f4f) and add it to your ~/.bash_profile file.

## Atom

As far as text editors go, I was a hardcore Sublime Text user, until I discovered Atom. There are lots of reasons why I switched to Atom. For starters I love how easy it is to install packages and themes. Sublime was lightning fast and if Atom catches up I don't think I'll be going back to Sublime (but we had a great run)! [Atom](https://atom.io/) is currently my favorite text editor.

Other text editors: [Sublime Text](https://www.sublimetext.com/), [Visual Studio Code](http://code.visualstudio.com/), [Brackets](http://brackets.io/) 

Installed Packages: language-babel, atom-beautify, autohide-tree-view, color-picker, emmet, minimap, pigments, javascript-snippets
Fav Themes: UI Theme (One Dark), Syntax Theme (Oceanic Next or Green)

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

It is high time I give credit to the excellent mac-dev-setup instructions of [nicholashery](https://github.com/nicolashery/mac-dev-setup). I will refer you to his page to read up on how to use Homebrew to install packages. For my own quick reference:
- Check if brew is installed: `brew --version`
- To see where it's installed: `which brew`
- Always keep homebrew updated: `brew update`
- To see what was installed using homebrew: `brew list`
- To uninstall software: `brew uninstall packagename`
- To check which packages are out of date: `brew outdated`
- To not update specific software package: `brew pin packagename` Then run the update. Can also upnpin package.
- To upgrade specific packages: `brew upgrade packagename`

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

Add basic git configurations that will be added to your `.gitconfig` file. You can also add aliases to your config file similar to the ones I use in the example file. (TODO: add example file)

    $ git config --global user.name "Your Name Here"
    $ git config --global user.email "your_email@youremail.com"

Also create a `.gitignore` file. Look at the example file. (TODO: add example file)
Here is a fun website that teaches the [basics of how to use git](http://rogerdudler.github.io/git-guide/).

## LESS

[LESS](http://lesscss.org/) is a CSS preprocessor that makes it easier to organize and reuse CSS code. I use it because it is what I'm most familiar with but [SASS](http://sass-lang.com/) is also very popular among Ruby developers. I think I'll be moving into CSS Modules for React soon which will make LESS and SASS obsolete.

## Project Folders

I usually put my version controlled projects in `~/Projects`.
I usually put my non-version controlled projects in `~/Dropbox`.

## Tech Stacks

I have a few different tech stacks that I use.
- JavaScript applications: **MERN** (MondoDB, Express, React, Node)
- Wordpress projects hosted on my VPS: **LAMP** (Linux, Apache, MariaDB, PHP)
- Local PHP development: **MAMP** (Apache, MySQL, PHP)

Variations to the stack choices above can include:
- NGINX for Apache
- Databases: mySQL, MariaDB, MongoDB, PostgreSQL
- Python for PHP

### React.js

So far my favorite Javascript library is [React](https://facebook.github.io/react/). I won't list them all but some of the modules I use with React projects include **react-router, babel, gulp, lodash, less, webpack, eslint, redux, reselect,** and **redux-devtools**.

Here are the steps I take to setup a React project:

#### Node.js

Make sure Node.js is installed.
With Homebrew installed just run the following:

    $ brew install node
    
Then check to see if node is installed by running: `node -v`. Check if npm is installed by running: `npm -v`
Note 1: I didn't have issues but if you do, don't use homebrew and install manually.
Note 2: If you need to use different node versions on your machine install nvm (node version manager) 

#### Install Node Modules

THE NPM WAY:
If your starting a new project:
- Create your first React index.html file. 
- In the root directory for that project run `npm init` to create a new node_modules directory and package.json file.

If your working on an existing project:
- do a git clone to pull down the repo files to your local directory.
- run `npm install` so you can add all the necessary module dependencies and update the package.json file with these dependencies.

You may (should) include these npm modules in your React project. Since you'll use them for all React development you can install them globally. (Standard is optional and mocha might be replaced with another testing tool soon).
- npm install -g mocha
- npm install -g nodemon
- npm install -g webpack
- npm install -g standard

Here are your two must have React project modules. Install them in each project directory.
- npm install react react-dom

THE YARN WAY:
**NOTE:** I typically use **Yarn** instead of npm to install all React project dependencies. (See the section on Yarn below).
To initialize a new project use `yarn init` and fill out the prompts which will create a new package.json file. 
You can also run `yarn add <package name>` to save your dependencies to package.json. 
Add `--dev` to this command to save to devDependencies.

#### NPM Scripts
Open your package.json file and add bash commands to make your longer commands shorter and easier to remember.
The word on the left can be anything you want but these are standard ones. The command on the right is what will actually run.

    "scripts": {
        "build": "webpack"
        "start": "node server.js"
        "lint": "eslint --ignore-path .gitignore --cache ./"
     }

To run this on command line for example you could run: `$ npm run build` which will run webpack.
For special words like "test" and "start" running `npm test` or `npm t` will also work.

#### Babel

Babel takes es6 (future JavaScript) and compiles it down to es5 (current JavaScript), the version currently supported on the majority of browsers.

Install by first addding the dependencies:
*The last two packages will allow you use start using es6 and JSX*.

    $ yarn add babel-loader babel-core babel-preset-es2015 babel-preset-react
    
Now create a new file named `.babelrc`.
Inside write the following JSON.
    
    {
        'presets': [
            'es2015', 'react'
        ]
    }

If you were still using npm scripts to run webpack you would change the command to the following:
`"build": "webpack --module-bind 'js=babel' js/ClientApp.js public/bundle.js"`

However this is getting long so you should change remove everything after webpack and set up a webpack config file described in the next section.

#### Webpack

Webpack takes all components that you’ve created puts it together in one bundled JavaScript file and makes it available to send down.
That way you can break huge projects down to smaller more manageable modules. 
To install: 

    $ yarn add webpack webpack-dev-server path (or run $ npm install --global webpack)
    
Now you could run a command to convert your React files into your final js file. Make sure you are in your project's root directory. 
For a Dev build, run:
  
    $ webpack js/Clientapp.js public/bundle.js
    
In this example the first file webpack is going to see is js/Clientapp.js. The output file will be public/bundle.js.
The bundle.js file will be pretty large. That is why you should run a separate build for production. This one should be minified, gzipped.
For a Produciton build, run: 

    $ NODE_ENV=production webpack -p js/Clientapp.js public/bundle.js 
 
Now all you need to do is add the file path to your bundle file in your main html file.
You could add this command to your npm scripts. However it will get even longer once you add Babel.
Instead of running longer commands like this, you can create a webpack config file to handle it for you.

Create a new *webpack.config.js* file in the project root directory.
Add the following:

    const path = require('path')
    module.exports = {
        entry: 'app.js',
        output: {
            path: path.resolve('dist'),
            filename: 'bundle.js'
        },
        module: {
            loaders: [
                {test: /\.js$/, loader: 'babel-loader', exclude: /node-modules/}
            ]
        }
    }
    
Entry: is the file where the bundler starts the bundling process.
Output: is the location where the bundled JS file will be saved.
Loaders: are transformations applied on a file in our app. The key property takes on an array of loaders.

Check the [Webpack documentation](https://webpack.github.io/docs/list-of-loaders.html) for more potential loaders you can use.
With the webpack config file setup all you have to do is run `npm run webpack` when you want to push out a build.

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

## List of Tools

These are either some of the tools that I use and others that I'd like to explore:

### Yarn

[Yarn](https://yarnpkg.com/en/) is a great package manager that installs packages for your projects. It's 100% deterministic, installs packages faster and has better caching than npm. Yarn locks down your dependencies by default (as opposed to npm shrinkwrap command which is more difficult to maintain). General rule is use Yarn for individual project installs and npm for library project installs or global installs where you may not want to lock down the dependencies.

To install it run `brew install yarn`.

To install a project's dependencies go to the project directory and run `yarn` (similar to npm install command). You'll see a list of dependencies being installed. A yarn.lock file will be created that automatically gets updated when you run yarn commands. If it's a new project with no dependencies yet run `yarn init` and answer the series of questions.

To add packages run `yarn add packagename`. 
A yarn.lock file will be created which locks down the exact dependencies to use on another machine. Don't modify this file.

Cool fact: you can run `yarn upgrade-interactive` to see all the packages for your project for which upgrades are available.

### Standard

This takes the esLint tool to another level. [Standard](https://standardjs.com/) is everything you loved about esLint but with a standard set of rules (including no semicolons!) 

Install: `npm install --global standard`.
To Use: While in your project directory run `standard` in terminal.
To Fix: Run `standard --fix` to fix some of the linting errors. 

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
