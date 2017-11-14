
Often I come around, using my Mac in a mixed network environment. Especially annoying in such environments is the default behaviour of OSX writing .DS_Store files all over the place and especially to connected shared folders of your Linux or Windows boxes. These hidden files used to store custom attributes of a folder such as the position of icons or the choice of a background image.

While this is ok in OS X it’s annoying for network shares. To prevent the creation of .DS_Store files on network volumes:

 defaults write com.apple.desktopservices DSDontWriteNetworkStores true

In addition, to get rid of all already existing .DS_Store files:

 sudo find / -name '.DS_Store' -print -delete


