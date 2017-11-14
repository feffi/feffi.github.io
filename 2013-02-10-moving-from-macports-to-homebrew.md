
If you ever want to move from [MacPorts](http://www.macports.org "MacPorts") to [Homebrew](http://mxcl.github.com/homebrew/ "Homebrew") your could feel a little bit scared though MacPorts has tons of compiled stuff on your system.

But fortunately the way of migrating to [Homebrew](http://mxcl.github.com/homebrew/ "Homebrew") is rather simple:  
 First, uninstall MacPorts:

sudo port -f uninstall installed

Next step: Back up all stuff in /opt/local/ you need (like MySQL, php.ini, etc.).  
 Last step: Clean up everything that’s left from [MacPorts](http://www.macports.org "MacPorts").

 sudo rm -rf /opt/local sudo rm -rf /Applications/DarwinPorts sudo rm -rf /Applications/MacPorts sudo rm -rf /Library/LaunchDaemons/org.macports.* sudo rm -rf /Library/Receipts/DarwinPorts*.pkg sudo rm -rf /Library/Receipts/MacPorts*.pkg sudo rm -rf /Library/StartupItems/DarwinPortsStartup sudo rm -rf /Library/Tcl/darwinports1.0 sudo rm -rf /Library/Tcl/macports1.0 sudo rm -rf ~/.macports

As an secure alternative, all directories could be moved to a secure location instead of being deleted directly. After that you should remove the `/opt/local/bin` from your `$PATH`.

Now install [Homebrew](https://github.com/mxcl/homebrew/wiki/installation) with the command:

 ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"

After bootstrapping [Homebrew](http://mxcl.github.com/homebrew/ "Homebrew") you can list packages

 brew search wget

and their respective options

 brew options wget

and finally even install them

 brew install wget


