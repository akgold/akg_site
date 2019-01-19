+++
author = "Alex K Gold"
categories = ["web-development", "github"]
date = "2017-05-01"
description = ""
featured = "namecheap.png"
featuredalt = "namecheap"
featuredpath = "date"
linktitle = ""
title = "Wedding?"
type = "post"

+++

If you know me personally, you know that aside from being a huge data nerd, I am totally crazy about my fiancee, Shoshana. Thus I'm SO happy that I get to build a [wedding website](http://shoshandalex.fun) for us from scratch.

In order to not have to learn a totally new technology, I set it up as a github project page with a custom URL. A couple of interesting things I've learned:
* When you're setting up a website via [github pages](https://help.github.com/articles/using-a-custom-domain-with-github-pages/) with a *project* page, it's still really easy! On namecheap.com (my preferred domain server), you just set 2 `A` name records, one each to `192.30.252.153` and `192.30.252.154` and one `CNAME` record to your main github pages site `username.github.io`. Then, create a file called `CNAME` in the repo that includes just the registered domain. Really easy! Wait 5-10 minutes for DNS servers to refresh and you're good to go!

_My namecheap.com setup_
![](/img/2017/namecheap.png)

_The setup in `CNAME`_
![](/img/2017/cname.png)



* Setting up a subdomain is really easy. Say I wanted to create a section of my website for the bachelor party available at `shoshandalex.fun/bachelor`. This is as easy as copying my `index.html` file to `bachelor.html` and editing that file to serve whatever I want on the bachelor party page. Makes it really easy to house different content on the sub-pages with consistent style. It's cool when tools are well designed!
* Doing RSVP forms in Jekyll isn't totally trivial. Still working on getting that set up...
