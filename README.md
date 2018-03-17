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

## Visual Studio Code

As far as text editors go, I was a hardcore [Sublime Text](https://www.sublimetext.com/) user, then I used [Atom](https://atom.io/) and now I'm loving [Visual Studio Code](http://code.visualstudio.com/).

I love the embedded terminal, ease of installing packages, and debug features.

Installed Packages: Babel ES6/ES7, ESLint, Flow Language Support, Prettier - Code formatter.

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

### React JavaScript Projects

So far my favorite Javascript library is [React](https://facebook.github.io/react/). 
Here are the steps I take to setup a new React project:

#### Install/Update Node.js

Node is a server framework that allows for asynchronous JavaScript programming on the server. Node files (.js files) must be initiated in the command line. You can include modules in your application. Most notably is NPM (a package manager for Node).

Make sure Node.js is installed. With Homebrew just run the following:

    $ brew install node
    
Verify you have node installed: `node -v`
Verify you have npm installed: `npm -v`

Note 1: I didn't have issues but if you do, don't use homebrew and install node manually.
Note 2: If you need to use different node versions on your machine install [nvm](https://github.com/creationix/nvm) (node version manager). Verify it's installed by running: `command -v nvm`.
Use this [web page](https://davidwalsh.name/nvm) to learn how to easily use nvm. 

#### Update NPM to latest version

NPM comes installed with Node.js. 
To update npm to the latest version run: `npm install -g npm@latest`

#### Install Yarn Globally

When NPM 4 was the latest, Yarn was a must because it produced a yarn.lock file that NPM didn't. There was no need to use messy shrinkwrap files. Instead Yarn locked down your dependencies for easy management. Now that NPM 5 is in use, the only real benefit of Yarn is that it still builds dependencies faster than NPM. When NPM improves speed I'll switch back to it. Until then I'll continue using Yarn.

    $ npm install --global yarn
    
Then check that you installed it properly.

    $ yarn --version

#### Create/Install Node Modules

New projects:

- Create your first React index.html file. 
- In the root directory for that project run the following to create a new node_modules directory and package.json file.
    
 `npm init` or `yarn init`
    
Existing projects:

- Run `git clone path-to-project` to pull down the repo files to your local directory.
- Run the following to add module dependencies listed in the package.json file. A package-lock.json  or yarn.lock will be created.

 `npm install` or `yarn`

Save a new dependency:
 
 `npm install <package name>` or `yarn add <package name>`

Add `--dev` to this command to save to devDependencies.

#### Install React and React-Dom

For any new React projects I'll typically install the following:

 `npm install react react-dom`
 
Other good packages I use with my projects can be found in this [package.json template](). 

#### Install Prettier and ESLint

Prettier is a style formatter for your project files. To install:

    $ npm install --global prettier
    
ESLint is a JavaScript linting tool. To install:

    $ npm install --global eslint

Can also install them in your project by adding all the eslint dependencies to package.json.

#### Set up ESLint config file

Create a file in your root directory named .eslintrc.json.
Fill it with the config code setup from this template.
Add a bash command "lint" in your NPM scripts file shown below.

You can test this by running the command: `yarn lint`.

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

#### Create index.html and app.js

Add a index.html and make sure it has at least one div with id="app".
Add script tag with src="js/bundle.js"

Add app.js file. This will contain your import statements for react and react-dom {render}.

#### Babel

Babel takes es6 (future JavaScript) and compiles it down to es5 (current JavaScript), the version currently supported on the majority of browsers.

Install by addding the dev dependencies below:

    $ yarn add babel-loader babel-core babel-eslint babel-plugin-dynamic-import-node babel-plugin-syntax-dynamic-import babel-plugin-transform-class-properties babel-plugin-transform-es2015-modules-commonjs babel-preset-env babel-preset-react --dev 

#### Write config file for Babel

Now create a new file named `.babelrc` in the root directory.
Copy the [template presets for Babel](). Inside this file you set presets which are groups of plugins. Plugins are the transformation tools.

Note: If you were still using npm scripts to run webpack you would change the command to the following:
`"build": "webpack --module-bind 'js=babel' js/ClientApp.js public/bundle.js"`

However this is getting long so you should change remove everything after webpack and set up a webpack config file described in the next section.

#### Webpack

Webpack takes all components that you’ve created puts it together in one bundled JavaScript file and makes it available to send down. That way you can break huge projects down to smaller more manageable modules. 

To install: 

    $ yarn add webpack (or run $ npm install --global webpack)
    
Now you could run a command to convert your React files into your final js file. Make sure you are in your project's root directory. 
For a Dev build, run:
  
    $ webpack js/Clientapp.js public/bundle.js
    
In this example the first file webpack is going to see is js/Clientapp.js. The output file will be public/bundle.js.
The bundle.js file will be pretty large. That is why you should run a separate build for production. This one should be minified, gzipped.
For a Produciton build, run: 

    $ webpack -p js/Clientapp.js public/bundle.js 

#### Write config file for Webpack

Now all you need to do is add the file path to your bundle file in your main html file.
You could add this command to your npm scripts. However it will get even longer once you add Babel.
Instead of running longer commands like this, you can create a webpack config file to handle it for you.

Create a new *webpack.config.js* file in the project root directory.
Fill out the config based on the [webpack config template]().
 
EXPLANATION OF CONFIG FILE:
Context: sets the root directory.
Entry: is the file where the bundler starts the bundling process.
Output: is the location where the bundled JS file will be saved.
Devtool: Uses source maps.
Resolve: Tells webpack which files to add to bundle and in a particular order.
Stats: Info configuration.
Module: Rules for webpack.
Loaders: are transformations applied on a file in our app. The key property takes on an array of loaders.

Check the [Webpack documentation](https://webpack.github.io/docs/list-of-loaders.html) for more potential loaders you can use.

#### Set bash commands for Webpack

Create a bash command "build": "webpack" in npm scripts for webpack. It will know to use the config file settings.
Test the command by running `yarn build` or `npm run build`.

Now instead of building every time you make a change, set up the watcher bash command to build every time you save your files.
Add "start": "webpack --watch" to your package.json scripts.

#### LESS

[LESS](http://lesscss.org/) is a CSS preprocessor that makes it easier to organize and reuse CSS code. I use it because it is what I'm most familiar with but [SASS](http://sass-lang.com/) is also very popular among Ruby developers. I think I'll be moving into CSS Modules for React soon which will make LESS and SASS obsolete.

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
