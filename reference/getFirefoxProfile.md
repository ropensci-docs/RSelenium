# Get Firefox profile.

`getFirefoxProfile` A utility function to get a firefox profile.

## Usage

``` r
getFirefoxProfile(profDir, useBase = TRUE)
```

## Arguments

- profDir:

  The directory in which the firefox profile resides

- useBase:

  Logical indicating whether to attempt to use zip from utils package.
  Maybe easier for Windows users.

## Detail

A firefox profile directory is zipped and base64 encoded. It can then be
passed to the selenium server as a required capability with key
firefox_profile

## Examples

``` r
if (FALSE) { # \dontrun{
fprof <- getFirefoxProfile("~/.mozilla/firefox/9qlj1ofd.testprofile")
remDr <- remoteDriver(extraCapabilities = fprof)
remDr$open()
} # }
```
