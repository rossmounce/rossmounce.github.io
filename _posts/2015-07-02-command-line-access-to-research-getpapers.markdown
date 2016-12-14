---
author: rmounce
comments: true
date: 2015-07-02 14:53:13+00:00
layout: post
link: http://rossmounce.co.uk/2015/07/02/command-line-access-to-research-getpapers/
slug: command-line-access-to-research-getpapers
title: 'Command-line access to research: getpapers'
wordpress_id: 1838
categories:
- Content Mining
- Open Science
---

With a first commit to github not so long ago ([2015-04-13](https://github.com/ContentMine/getpapers/commit/be2aed7cf9b3362f5cc759ff880d8407ee6a6c71)), _getpapers_ is one of the newest tools in the [ContentMine](http://contentmine.org/) toolchain.

It's also the most readily accessible and perhaps most immediately exciting - it does exactly what it says on the tin: it **gets papers** for you _en masse_ without having to click around all those different publisher websites. A superb time-saver.

It kinda reminds me of [mps-youtube](https://github.com/mps-youtube/mps-youtube): a handy CLI application for watching/listening to youtube.

Installation is super simple and usage is well documented at the source code repository on [github](https://github.com/ContentMine/getpapers/), and of course it's available under an [OSI-approved](http://opensource.org/licenses) open source MIT license.

[caption id="" align="alignnone" width="1394"]![](https://raw.githubusercontent.com/ContentMine/getpapers/master/docs/screenshot.png) An example usage querying Europe PubMedCentral[/caption]

Currently you can search 3 different aggregators of academic papers: [Europe PubMedCentral](http://europepmc.org/), [arXiv](http://arxiv.org/), and [IEEE](http://ieeexplore.ieee.org/Xplore/home.jsp). Copyright restrictions unfortunately mean that full text article download with _getpapers_ is restricted to only freely accessible or open access papers. The development team plans to add more sources that provide API access in future, although it should be noted that many research aggregators simply don't appear to have an API at the moment e.g. [bioRxiv](http://biorxiv.org/).

The speed of the overall process is very impressive. I ran the below search & download command and it executed it all in 32 seconds, _including_ the download of 50 full text PDFs of the search-relevant articles!

    
    getpapers --query 'flaveria c4' -p --outdir test



You can choose to download different file formats of the search results: PDF, XML or even the supplementary data. Furthermore, _getpapers_ integrates extremely well with the rest of the ContentMine toolchain, so it's an ideal starting point for content mining.

_getpapers_ is one of many tools in the ContentMine toolchain that I'll be demonstrating to early career biologists at a FREE registration, one-day workshop at the University of Bath, Tuesday 28th July. If you're interested in learning more about _fully_ utilizing the research literature in scalable, reproducible ways, come along! We still have some places left. See the flyer below for more details or follow this link to the official workshop registration page: [bit.ly/MiningWrkshp](http://bit.ly/MiningWrkshp)

[![mining-flyer](http://rossmounce.co.uk/wp-content/uploads/2015/07/mining-flyer-825x1024.png)](http://rossmounce.co.uk/wp-content/uploads/2015/07/mining-flyer.png)
