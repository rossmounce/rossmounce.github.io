---
author: rmounce
comments: true
date: 2014-07-04 12:53:00+00:00
layout: post
link: http://rossmounce.co.uk/2014/07/04/steganography-phylogenetics-and-flickr/
slug: steganography-phylogenetics-and-flickr
title: Steganography, phylogenetics and Flickr
wordpress_id: 1444
categories:
- PLUTo
---

**How best to link the figure, to the paper & the underlying data?

**Whilst visiting EBI, Hinxton yesterday, [Robert Hanson](http://www.stolaf.edu/people/hansonr/) (computational chemist) reminded me of an interesting hack you can do to embed data in images.

Back in 2010 it was [widely reported that people were using Flickr to transmit data (secretly) in images](http://www.newscientist.com/article/dn19284-hiding-files-in-flickr-pics-will-fool-web-censors.html).

This general technique is called **[Steganography](http://en.wikipedia.org/wiki/Steganography).**

Turns out I can use this hack in my project too...

As a proof of concept, I've uploaded one recent PLOS ONE phylogeny figure to my 'plosone-phylo' flickr account:

[https://www.flickr.com/photos/123621741@N08/14385231987/in/photostream/](https://www.flickr.com/photos/123621741@N08/14385231987/in/photostream/)

In this special file, I've embedded the nexus, NeXML & Bibtex file from [TreeBASE](http://treebase.org/treebase-web/search/study/summary.html?id=15461) that correspond to the image. This [website](http://wiki.linuxquestions.org/wiki/Embed_a_zip_file_into_an_image) has cross-platform instructions - it's remarkably simple.

So now if you download that special file I put on Flickr (this hack _only_ works if you download the original, not resized versions) and 'unzip' the image file you'll reveal the hidden data embedded in the image:  nexus, NeXML & Bibtex. 
**Try it!**

[caption id="attachment_1445" align="alignleft" width="774"][![Screenshot showing what to click to download the original image](http://rossmounce.co.uk/wp-content/uploads/2014/07/2014-07-04-134429_794x890_scrot.png)](http://rossmounce.co.uk/wp-content/uploads/2014/07/2014-07-04-134429_794x890_scrot.png) Screenshot showing what to click to download the original image[/caption]



This certainly isn't the 'optimal' way of doing things. But it is a nice way of keeping everything together in ONE file. Maybe you might have a use for this hack too?
