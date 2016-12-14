---
author: rmounce
comments: true
date: 2011-10-11 13:44:03+00:00
layout: post
link: http://rossmounce.co.uk/2011/10/11/research-tips-tricks-creating-rss-feeds-and-filters/
slug: research-tips-tricks-creating-rss-feeds-and-filters
title: Research Tips & Tricks – creating RSS feeds and filters
wordpress_id: 101
categories:
- phdchat
---

Yesterday’s post about haywire RSS feeds, reminded me that I should perhaps share a trick or two I know about RSS feeds.

This post assumes you know [what an RSS feed is](http://www.whatisrss.com/), and why they're awesome. I still encounter researchers everyday who have no idea what an RSS feed is. I have no idea how they cope with the sheer volume of literature being produced these days _without_ RSS feeds!

1.) RSS feed filtering

**why?**
Some journals e.g. [PLoS ONE](http://www.plosone.org/home.action) put out a *lot* of new research articles each and every week. So much so that it’s tiresome and time-wasteful to even read just the titles, let alone the abstracts of each and every new article published in this journal.

This should not be taken as a criticism of such high-volume journals. I’m very supportive of Open Access publishing, and the higher the volume of articles in Open Access rather than closed access, the better (for science) as far as I’m concerned. All one needs to do is apply some conservative filtering criteria to such feeds so that one receives _only_ items of interest.

**how?**
My interest is in [phylogenetics](http://en.wikipedia.org/wiki/Phylogenetics). Therefore I filter the [PLoS ONE new article (all subjects) alert feed](http://www.plosone.org/article/feed) by subject specific keywords using [Yahoo Pipes](http://pipes.yahoo.com/pipes/) (see below).
[![adge](http://farm7.static.flickr.com/6155/6234466508_3bc2665d90_z.jpg)](http://www.flickr.com/photos/63732388@N07/6234466508/)

If the wildcard filters for ‘phylo*’ and ‘clad*’ work, then the other filters are probably redundant, but just in case y’know.
The resultant output of this feed ([here](http://pipes.yahoo.com/pipes/pipe.run?_id=ba577229dc06a7e92d6cafe18e7a53e2&_render=rss)), significantly tames the PLoS ONE deluge to a relevant and manageable trickle.
There are many other ways of filtering RSS feeds, but the graphical nature of Yahoo Pipes IMO makes it very recommendable.

It’s worth noting as well that PLoS provide their own filtered feeds [here](http://www.plosone.org/static/rssFeeds.action) broken down by subject, but this isn’t helpful for me, as my research interest often pop-ups in many different subject classifications.

2.) RSS feed creation

**why?**
Perhaps a [journal](http://roddymacleod.wordpress.com/2010/04/06/many-open-access-oa-journals-dont-have-table-of-contents-rss-feeds-and-they-are-therefore-missing-out-a-great-deal/) / [database](http://www.morphobank.org/) / website of interest to you doesn’t provide an RSS feed. So you can’t otherwise easily track updates to it. With research, I think it’s very important to keep up to date with the latest developments. Journals, databases and websites *should* of course always provide RSS feeds for you but a minority in my experience don’t.

The solution for these cases is: DIY!

**how?**
Again there are a huge swathe of options to help you ‘roll your own’ RSS feed. Some are reasonably complex and highly configurable e.g. [http://feed43.com/](http://feed43.com/) Whilst others are really simple, but not so adaptable e.g. [http://page2rss.com/](http://page2rss.com/)

The latter, simple option works very well for me, so I can keep up to date with latest additions to the [MorphoBank](http://www.morphobank.org/) database.

I’d be interested to know if anyone had any further recommendations for RSS feed creation tools, other RSS-related tips & tricks and/or interesting research related use-cases.

PS Should anyone wish to subscribe to my output, the RSS feed for this blog is [here](http://rossmounce.co.uk/feed/) (and in the top right hand corner, I should probably make it a bit more obvious though!)

Further Reading:

[http://iphylo.blogspot.com/2009/07/how-to-publish-journal-rss-feed.html](http://iphylo.blogspot.com/2009/07/how-to-publish-journal-rss-feed.html)
