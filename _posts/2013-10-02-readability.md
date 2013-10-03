---
layout: post
title: "Readability"
description: "Code to take an html journal article and send it to kindle through readability"
category: "code"
tags: ["ruby", "kindle", "readability"]
---
{% include JB/setup %}

Today, I worked through finishing a script that would allow me to take a local html journal article, transform it to text via readability, and then send it to my kindle. I started on this script a few days back and had hoped to be done today but there seem to be some final touches left. Here, I'll detail the specific steps involved and any trouble that I faced.

Why am I taking all these steps? First, I really enjoy reading off the kindle and believe it increases my productivity. I find it at least doubles my reading speed and it is easier to use then an iPad or easier to look at then an iPhone especially when traveling (e.g., on the train or subway). Second, I can't use many send to kindle options for scientific articles. Most articles require a login or institutional access and options such as readability or instapaper try to scrape these pages from their servers, which won't have access. Consequently, I'm taking a round-a-bout approach here by getting the text from the article via my access, then posting it online, and saving it to the kindle from there with readability (although other options like instapaper or pocket should work just as well).

# Saving Journal Article

Assuming I have access to the article (e.g., via Yale vpn access), then I save the article from the browser using a single-click Zotero plugin. This imports the citation, pdf, and snapshot (full html page) of the specified paper. In order to get the full page snapshot, I need to make sure to always be on the full text page and not just the abstract page. I can note the location of the snapshot by right-clicking it in Zotero and finding it in the Finder.

# Uploading HTML Journal Article to Web Server

This is a simple `scp` command. I am using a web server to temporarily copy the html page of the journal article to the web. I use an ssh key allowing me to skip entering a password every time.

## Problems

The only issue I faced was that one needs `sudo` access to copy files to the public web folder. As a workaround, I soft-linked from an external folder to which I would have user access.

# Sending the HTML to Readability

Here I made a simple script (you can view it as a [github gist](https://gist.github.com/czarrar/6805001)) that makes use of readit to add a bookmark on readability for the desired web page. In this case, the web page is the recently uploaded page. This script returns the article id of the newly bookmarked page.

## Problems

The first problem I faced was how I could login to readability. Two types of tokens are needed when using readit: consumer tokens and user tokens. The consumer tokens are easily accessible off of the readability site. The user tokens, however, appear to require actually logging into the site. I figured out how to do this by using oauth and the x_auth method of giving my username and password along with the consumer tokens. This then gives me access to the consumer tokens. This knowledge came from a github gist that should be cited here when I remember it.

I also recently encountered a problem where if I add a bookmark and then update the original page, I can't seem to then update the bookmark. The content of the bookmark will be of the original page and not the new page. Deleting the bookmark doesn't seem to help here either. So TBD.

# Sending Readability Bookmark to Kindle

Here I made another simple script that makes use of mechanize and nokogiri to manually access the readability site and send a specific bookmarked article to kindle. This script can also be viewed as a [github gist](https://gist.github.com/czarrar/6805097).

## Problems

I had tried to send to kindle with the more convenient readit  library. However, for some reason I got some error any time I tried to access the kindle api page, which seems to be labeled as legacy mode. I then found another repository that took this more manual approach to interact with readability.