
This one is a little techie, but nevertheless important for people who use their MacBook regulary. By default, only regular sleep (*suspend-to-disk*) is enabled. If you ever want to set another sleep mode, here you go:

##### always regular sleep (disable safe-sleep)

sudo pmset -a hibernatemode 0

##### always safe-sleep (disable regular sleep)

sudo pmset -a hibernatemode 1

##### regular sleep first, safe-sleep if the battery is very low on power or is unplugged

sudo pmset -a hibernatemode 3

##### always safe-sleep with secure virtual memory

sudo pmset -a hibernatemode 5

##### regular sleep first then safe-sleep with secure virtual memory

sudo pmset -a hibernatemode 7


