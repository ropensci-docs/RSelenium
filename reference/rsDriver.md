# Start a selenium server and browser

Start a selenium server and browser

## Usage

``` r
rsDriver(
  port = 4567L,
  browser = c("chrome", "firefox", "phantomjs", "internet explorer"),
  version = "latest",
  chromever = "latest",
  geckover = "latest",
  iedrver = NULL,
  phantomver = "2.1.1",
  verbose = TRUE,
  check = TRUE,
  ...
)
```

## Arguments

- port:

  Port to run on

- browser:

  Which browser to start

- version:

  what version of Selenium Server to run. Default = "latest" which runs
  the most recent version. To see other version currently sourced run
  binman::list_versions("seleniumserver")

- chromever:

  what version of Chrome driver to run. Default = "latest" which runs
  the most recent version. To see other version currently sourced run
  binman::list_versions("chromedriver"), A value of NULL excludes adding
  the chrome browser to Selenium Server.

- geckover:

  what version of Gecko driver to run. Default = "latest" which runs the
  most recent version. To see other version currently sourced run
  binman::list_versions("geckodriver"), A value of NULL excludes adding
  the firefox browser to Selenium Server.

- iedrver:

  what version of IEDriverServer to run. Default = "latest" which runs
  the most recent version. To see other version currently sourced run
  binman::list_versions("iedriverserver"), A value of NULL excludes
  adding the internet explorer browser to Selenium Server. NOTE this
  functionality is Windows OS only.

- phantomver:

  what version of PhantomJS to run. Default = "2.1.1" which runs the
  most recent stable version. To see other version currently sourced run
  binman::list_versions("phantomjs"), A value of NULL excludes adding
  the PhantomJS headless browser to Selenium Server.

- verbose:

  If TRUE, include status messages (if any)

- check:

  If TRUE check the versions of selenium available and the versions of
  associated drivers (chromever, geckover, phantomver, iedrver). If new
  versions are available they will be downloaded.

- ...:

  Additional arguments to pass to
  [`remoteDriver`](https://docs.ropensci.org/RSelenium/reference/remoteDriver-class.md)

## Value

A list containing a server and a client. The server is the object
returned by
[`selenium`](https://docs.ropensci.org/wdman/reference/selenium.html)
and the client is an object of class
[`remoteDriver`](https://docs.ropensci.org/RSelenium/reference/remoteDriver-class.md)

## Details

This function is a wrapper around
[`selenium`](https://docs.ropensci.org/wdman/reference/selenium.html).
It provides a "shim" for the current issue running firefox on Windows.
For a more detailed set of functions for running binaries relating to
the Selenium/webdriver project see the
[`wdman`](https://docs.ropensci.org/wdman/reference/wdman.html) package.
Both the client and server are closed using a registered finalizer.

## Examples

``` r
if (FALSE) { # \dontrun{
# start a chrome browser
rD <- rsDriver()
remDr <- rD[["client"]]
remDr$navigate("http://www.google.com/ncr")
remDr$navigate("http://www.bbc.com")
remDr$close()
# stop the selenium server
rD[["server"]]$stop()

# if user forgets to stop server it will be garbage collected.
rD <- rsDriver()
rm(rD)
gc(rD)
} # }
```
