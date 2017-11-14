
If you ever need to download your outdated packages for [Homebrew](http://mxcl.github.com/homebrew/ "Homebrew") at once for later installation, just try:
```
brew fetch `brew outdated | awk '{ print $1 }' | tr '\n' ' '`
```