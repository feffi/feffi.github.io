
There are many howtos and tutorials on how to install [nginx](http://nginx.com/ "nginx") on osx. I do not intend to clone one of these manuscripts, but to write down a quick and dirty approach on how to get [nginx](http://nginx.com/ "nginx") up and running fast. *Let’s start!*

Install newest [XCode](https://developer.apple.com/xcode/ "XCode")  
 Install [Command line tools via Xcode](http://stackoverflow.com/questions/9329243/xcode-4-4-command-line-tools "Command line utilities")  
 Install Homebrew

ruby <(curl -fsSk https://raw.github.com/mxcl/homebrew/go) sudo chown -R `whoami` /usr/local brew update brew doctor

Apply Mountain Lion Fixes for Homebrew

sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer

Install X11 v2.7.4+ from [XQuartz](http://xquartz.macosforge.org/trac/wiki "xquartz")

sudo ln -s /opt/X11 /usr/X11 nano /etc/profile PATH=/usr/local/bin:/usr/local/opt/php54/bin:$PATH

remove apache from startup

sudo launchctl unload -w /System/Library/LaunchDaemons/org.apache.httpd.plist

and install [nginx](http://nginx.com/ "nginx")

(sudo gem install passenger) brew install nginx --with-webdav (--with-passenger) brew doctor (to check if all still fine in paradise!)

Make nginx log files visible in Console app

sudo mkdir /var/log/nginx

Create the following directorty to stop `/var/lib/nginx/speed failed (2: No such file or directory)` error

sudo mkdir /var/lib/nginx

install php

brew tap josegonzalez/homebrew-php brew tap homebrew/dupes brew install php54 --with-fpm --with-imap --with-mariadb chmod -R ug+w /usr/local/Cellar/php54/5.4.10/lib/php pear config-set php_ini /usr/local/etc/php/5.4/php.ini brew install php54-apc php54-geoip php54-http php54-mcrypt php54-memcache php54-memcached php54-oauth php54-pcntl php54-ssh2 php54-uuid

make php startup

mkdir -p ~/Library/LaunchAgents cp /usr/local/Cellar/php54/5.4.10/homebrew-php.josegonzalez.php54.plist ~/Library/LaunchAgents/ ln -sfv /usr/local/opt/php54/*.plist ~/Library/LaunchAgents launchctl load -w ~/Library/LaunchAgents/homebrew-php.josegonzalez.php54.plist

You may also need to edit the PHP plist to use the correct “UserName”

After that, configure PHP

and php-fpm params

and nginx global config

install nginx SSL certificates

cd /usr/local/etc/nginx/ mkdir ssl cd ssl openssl req -new -x509 -nodes -out server.crt -keyout server.key chmod 600 server.key

mimic debian site structure loading

mkdir /usr/local/etc/nginx/sites-available mkdir /usr/local/etc/nginx/sites-enabled cd /usr/local/etc/nginx/sites-available nano localhost.conf

enable global site

cd /usr/local/etc/nginx/sites-enabled ln -s /usr/local/etc/nginx/sites-available/minibunker.conf .

reload nginx

nginx -s reload

install the mariadb

brew install mariadb --enable-local-infile --with-archive-storage-engine --with-blackhole-storage-engine --use-llvm --env=std

Mountain Lion comes with php-fpm pre-installed, to ensure you are using the brew version you need to make sure `/sbin` is before `/usr/sbin` in your `PATH`:

PATH="/sbin:$PATH"

#### **Done!**

#### References

- [Install Nginx and PHP on OS X Mountain Lion (10.8) – Group 7even Blog](http://www.group7even.com/blog/2012/02/23/installing-nginx-php-fpm-on-os-x-mountain-lion-10-8/)
- [<span style="line-height: 1.7;">Installing nginx in Mac OS X Mountain Lion with homebrew – Learn-a-holic Geek Notes</span>](http://learnaholic.me/2012/10/10/installing-nginx-in-mac-os-x-mountain-lion/)
- <span style="line-height: 1.7;">[nginx / MariaDB / PHP / Aegir on Mac OS X with optional Drush 5 (works on Mountain Lion!)](http://realityloop.com/blog/2012/07/03/nginx-mariadb-php-aegir-mac-os-x-optional-drush-5-works-mountain-lion)</span>


