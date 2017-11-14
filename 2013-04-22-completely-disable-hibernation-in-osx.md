
Since MacOS X 10.8.2 a major glitch could render your MacBook useless, by randomly vanishing icons on your Desktop bar. To circumvent this, hibernation (deep sleep) can be turned off completely:
```
sudo pmset -a hibernatemode 0
```
Then remove the hibernation file  
```
sudo rm /Private/var/vm/sleepimage
```
To prevent a recreation of this file, create a blank zero-byte immutable file so OS X cannot rewrite the file.  
```
sudo touch /Private/var/vm/sleepimage
sudo chflags uchg /Private/var/vm/sleepimage
```
**Attention**: This means you could never use hibernation (deep sleep)!