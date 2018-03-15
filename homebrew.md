# Homebrew
I use this when installing programs to my Mac operating system.

## Install
I already had Xcode installed on my machine. I just needed to install the Command Line Tools. (Note: Newer OS X versions will no longer require you to download CLT or Xcode for this step).

    $ xcode-select --install
  
To check the command line tools version run this:

    $ xcode-select --version
  
Now install Homebrew:

    $ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  
You should run the following command to make sure there are no issues you need to correct with Homebrew:

    $ brew doctor

## Usage

It is high time I give credit to the excellent mac-dev-setup instructions of [nicholashery](https://github.com/nicolashery/mac-dev-setup). I will refer you to his page to read up on how to use Homebrew to install packages. For my own quick reference:
- Check if brew is installed: `brew --version`
- To see where it's installed: `which brew`
- Always keep homebrew updated: `brew update`
- To see what was installed using homebrew: `brew list`
- To uninstall software: `brew uninstall packagename`
- To check which packages are out of date: `brew outdated`
- To not update specific software package: `brew pin packagename` Then run the update. Can also upnpin package.
- To upgrade specific packages: `brew upgrade packagename`
