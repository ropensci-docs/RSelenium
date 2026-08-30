# Make Firefox profile.

`makeFirefoxProfile` A utility function to make a firefox profile.

## Usage

``` r
makeFirefoxProfile(opts)
```

## Arguments

- opts:

  option list of firefox

## Note

Windows doesn't come with command-line zip capability. Installing rtools
<https://CRAN.R-project.org/bin/windows/Rtools/index.html> is a
straightforward way to gain this capability.

## Detail

A firefox profile directory is zipped and base64 encoded. It can then be
passed to the selenium server as a required capability with key
firefox_profile

## Examples

``` r
if (FALSE) { # \dontrun{
fprof <- makeFirefoxProfile(list(browser.download.dir = "D:/temp"))
remDr <- remoteDriver(extraCapabilities = fprof)
remDr$open()
} # }
```
