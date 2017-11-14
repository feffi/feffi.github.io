
If you need to manage more than your own host based on OSX it might become handy to reduce the data transfered over slow connections by RDP (aka screen sharing). The straightest method to archive this is by reducing the default color depth used by RDP.

 $ defaults write com.apple.ScreenSharing controlObserveQuality [1|2|3|4|5]

The following codes are available:

- 1 = black and white
- 2 = grayscale
- 3 = 8-bit color
- 4 = 16-bit color
- 5 = full color


