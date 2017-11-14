
Sometimes the [Steam client](http://store.steampowered.com/about/ "Steam client") can be really annoying. Especially when it comes to broken updates. After such an update failure, you can keep clicking on your clients start icon, the update progress meter pops up and BOOM (or not), your client silently crashes without any notification.

After a while messing around with the applications settings I found a rather trivial way to compensate this problem:  
```
rm -f '~/Library/Application Support/Steam/.crash'
```
Just after deletion of this file, the [Steam client](http://store.steampowered.com/about/ "Steam client") starts up like normal. Have fun!

