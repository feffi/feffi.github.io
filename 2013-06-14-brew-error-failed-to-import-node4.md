
If you sporadically like me test your [Homebrew](https://github.com/mxcl/homebrew) installation with `brew doctor`, sometimes you run into errors and glitches. One of these errors is
```
Error: Failed to import: node4
```

This can be fixed with the following steps:
```
brew prune
brew cleanup
brew update
brew tap --repair
brew doctor
```
After this your brew installation should be gotten rid of this error.

