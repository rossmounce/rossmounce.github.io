---
author: rmounce
comments: true
date: 2015-06-14 18:11:56+00:00
layout: post
link: http://rossmounce.co.uk/2015/06/14/progress-on-specimen-mining/
slug: progress-on-specimen-mining
title: Progress on specimen mining
wordpress_id: 1823
categories:
- Content Mining
---

I've been on holiday to Japan recently, so work came to a halt on this for a while but I think I've largely 'done' PLOS ONE full text now (excluding supplementary materials).

My results are on github: [https://github.com/rossmounce/NHM-specimens/tree/master/results](https://github.com/rossmounce/NHM-specimens/tree/master/results) - one prettier file without the exact provenance or in-sentence context of each putative specimen entity, and one more extensive file with provenance & context included which unfortunately github can't render/preview.



**Some summary stats:**

I found [427 unique BMNH/NHMUK specimen mentions](https://github.com/rossmounce/NHM-specimens/blob/master/results/plosone-cleaned.csv) from a total of just 69 unique PLOS ONE papers. The latter strongly suggests to me that there are a lot of 'hidden' specimen identifiers hiding out in difficult-to-search supplementary materials files.

I found 497 specimen mentions if you include instances where the same BMNH/NHMUK specimen is mentioned in different PLOS ONE papers.

Finding putative specimen entities in PLOS ONE full text is relatively automatic and easy. The time-consuming manual part is accurately matching them up with official NHM collection specimens data.

I could only confidently link-up 314 of the 497 detected mentions, to their corresponding unique IDs / URLs in the [NHM Open Data Portal Collection Specimens dataset](http://data.nhm.ac.uk/dataset/collection-specimens). Approximately one third can't be confidently be matched-up to a unique specimen in the online specimen collection dataset -- I suspect this is mainly down to absence/incompleteness in the online collections data, although a small few are likely typo's in PLOS ONE papers.

In [my last post](http://rossmounce.co.uk/2015/05/24/bmnh-specimens-used-in-plos-one/) I was confident that the BM _Archaeopteryx_ specimen would be the most frequently mentioned specimen but with more extensive data collection and analysis that appears now not to be true! [NHMUK R3592](http://data.nhm.ac.uk/specimen/ee332884-ff2a-4113-b734-d589d9340c89) (a specimen of _[Erythrosuchus africanus](https://en.wikipedia.org/wiki/Erythrosuchus)_) is mentioned in [5](http://dx.doi.org/10.1371/journal.pone.0034094) [different](http://dx.doi.org/10.1371/journal.pone.0072753) [PLOS](http://dx.doi.org/10.1371/journal.pone.0086864) [ONE](http://dx.doi.org/10.1371/journal.pone.0089165) [papers.](http://dx.doi.org/10.1371/journal.pone.0111388) Pleasingly, [Google Scholar also finds only five PLOS ONE papers mentioning this specimen](https://scholar.google.com/scholar?hl=en&q=NHMUK+R3592&btnG=&as_sdt=1%2C5&as_sdtp=) - independent confirmation of my methodology.

[caption id="" align="alignnone" width="800"]![](https://upload.wikimedia.org/wikipedia/commons/4/4e/Erythrosuchus_BW.jpg) One of the BM specimens of _Erythrosuchus_ is more referred to in PLOS ONE than the BM _Archaeopterx_ specimen[/caption]

Now I have these two 'atomic' identifiers linked-up (NHM specimen collections occurrence ID + the Digital Object Identifier of the research article in which it appears), I can if desired, find out a whole wealth of information about these specimens and the papers they are mentioned in.

My next steps will be to extend this search to all of the PubMedCentral OA subset, not just PLOS ONE.


