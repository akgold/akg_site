+++
author = "Alex K Gold"
categories = ["R", "web scraping", "packages"]
date = "2017-07-02"
description = "rvest is awesome for web scraping!"
linktitle = ""
title = "rvest is awesome for web scraping!"
type = "post"

+++

The [rvest](https://github.com/hadley/rvest) package is awesome. No surprise there, it's a Hadley Wickham jont. I'm in the early stages of a small project looking at goodreads quotes. I think I'm going to try to predict popular quotes. Then maybe I'll build a neural network to generate quotes trained on these. Stay tuned.

Anyway, I wanted to extract the top quotes on goodreads, and `rvest` made it super easy! I'd suggest [this tutorial](https://www.analyticsvidhya.com/blog/2017/03/beginners-guide-on-web-scraping-in-r-using-rvest-with-hands-on-knowledge/) for anyone just getting started.

### Minor Gripes
Just one complaint. Most tutorials suggest:

```r
url <- "myawesomeurl.com"
page <- rvest::html(url)
```

To get a page loaded for scraping.

If you do this now, you get a message saying that the `html` function has been deprecated and to use `read_html`. What it doesn't say is that `read_html` is from `xml2`, not `rvest`. Took me a little while of just saying f-it, I'll use the deprecated function before I found the secret of `read_html`. C'mon Hadley, I know you're amazing, but at least tell me what package the function's in.

### 12 Lines of Code
``` r
library(rvest)
wd <- "~/Documents/goodreads/"

url_stub <- "https://www.goodreads.com/quotes?page="

scrape_quotes <- function(url_stub, what, i) {
  print(paste0("Scraping page ", i, "."))
  page <- xml2::read_html(paste0(url_stub, i))
  rvest::html_nodes(page, what) %>% html_text()
}
quotes_raw <- lapply(1:100, function(i) scrape_quotes(url_stub, '.quote', i)) %>%
  unlist()
```
Then I have to do a bunch of regex-ing to clean up the quotes.

Note: It works fine if you just `library(rvest)` and then call `read_html()` without prefixing the function with a package at all. But that's bad form if you're writing a function.
