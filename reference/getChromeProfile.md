# Get Chrome profile.

`getChromeProfile` A utility function to get a Chrome profile.

## Usage

``` r
getChromeProfile(dataDir, profileDir)
```

## Arguments

- dataDir:

  Specifies the user data directory, which is where the browser will
  look for all of its state.

- profileDir:

  Selects directory of profile to associate with the first browser
  launched.

## Detail

A chrome profile directory is passed as an extraCapability. The data dir
has a number of default locations

- Windows XP:

  Google Chrome: C:/Documents and Settings/%USERNAME%/Local
  Settings/Application Data/Google/Chrome/User Data

- Windows 8 or 7 or Vista:

  Google Chrome: C:/Users/%USERNAME%/AppData/Local/Google/Chrome/User
  Data

- Mac OS X:

  Google Chrome: ~/Library/Application Support/Google/Chrome

- Linux:

  Google Chrome: ~/.config/google-chrome

The profile directory is contained in the user directory and by default
is named "Default"

## Examples

``` r
if (FALSE) { # \dontrun{
# example from windows using a profile directory "Profile 1"
cprof <- getChromeProfile(
  "C:\\Users\\john\\AppData\\Local\\Google\\Chrome\\User Data",
  "Profile 1"
)
remDr <- remoteDriver(browserName = "chrome", extraCapabilities = cprof)
} # }
```
