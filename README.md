# My Dev Setup
This is my attempt at documenting my personal development setup on both my local Mac OS X and remote Linux VPS. My aim is to use the local computer for developing JavaScript applications and other coding experiments. The remote Linux server is where I manage my Wordpress blogs. I hope to update this project file when I upgrade or add programs or packages to my dev setups. I'll also list technologies that I'm interested in learning or using soon.

I've borrowed from other github repositories for some of this information.

- [System update](#system-update)
- [System preferences](#system-preferences)
- [Google Chrome](#google-chrome)
- [iTerm2](#iterm2)
- [Atom](#atom)
- [Homebrew](#homebrew)

## System update

Before installing anything, make sure the operating system is updated to the latest version.
- For MAC: **Apple Icon > Software Update...**
- For Linux: Visit the official linux kernal website to determine what the current stable version of the kernal is. (More to come).

## System preferences

These are my personal changes to the System Preferences. (More to come).

## Google Chrome

Install your favorite browser, mine happens to be Chrome.
Download from [www.google.com/chrome](https://www.google.com/intl/en/chrome/browser/).

## iTerm2

Download and install [iTerm2](http://www.iterm2.com/) for a better terminal experience.
I like to change terminal preferences to add color and to see what branch I'm on. Take the code from this [gist](https://gist.github.com/nikkipurcell/2f8c0cc81c008a1a3ef7a35d82de0f4f) and add it to your ~/.bash_profile file.

## Atom

As far as text editors go, I was a hardcore Sublime Text user, until I discovered Atom. There are lots of reasons why I switched to Atom. For starters I love how easy it is to install packages and themes. Sublime was lightning fast and if Atom catches up I don't think I'll be going back to Sublime (but we had a great run)! [Atom](https://atom.io/) is currently my favorite text editor.

Other text editors: [Sublime Text](https://www.sublimetext.com/), [Visual Studio Code](http://code.visualstudio.com/), [Brackets](http://brackets.io/) 

## Homebrew

I use Homebrew as a package manager for when I need to install programs on my operating system. The process may change when I update my OS but as of (OS X Yosemite 10.10) you need to install **Command Line Tools** for **Xcode**. 

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


