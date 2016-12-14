---
author: rmounce
comments: false
date: 2012-08-04 22:49:08+00:00
layout: post
link: http://rossmounce.co.uk/2012/08/04/panton-fellowship-updates-july-month-4/
slug: panton-fellowship-updates-july-month-4
title: 'Panton Fellowship updates: July (month 4)'
wordpress_id: 354
categories:
- Content Mining
- Panton Fellowship updates
---

It's the Olympics now so this work update is a) late and b) short

Nevermind...

As ever progress has been exciting - look what we can extract from some PDFs:

[gallery columns="2" orderby="title"]

(click to enlarge each) Attribution: The left panel is from [Cánovas et al. BMC Evolutionary Biology 2011 11:371 doi:10.1186/1471-2148-11-371](http://www.biomedcentral.com/1471-2148/11/371)

On the left is the original figure, and on the right we have an SVG representation of the data we can extract automatically from this figure. We have the topology, the taxon labels AND the support values 100% correctly interpreted! Obviously we can't reclaim phylogenetic data with this much precision and recall from _all_ papers. But it's a promising example, automatically generated - no manual guidance or tweaking needed - just feed it the PDF. [My Wordpress server won't let me upload the original SVG copy of this for "security reasons" so the image on the right is a .jpg copy of the original .svg]



I should also note this was achieved completely independently of previous image-based tree-extraction softwares like TreeSnatcher Plus, TreeRipper & TreeThief. This is a great example of why it's _very_ important for editors and publishers to strictly stipulate that diagrams in figures containing data such as this be uploaded and produced in the final PDF version as lossless vector graphics rather than lossy bitmaps such as .png .jpg or .bmp - only vectors keep the fidelity of the underlying data. We note that there are many publishers out there who regularly seem to produce figures in their PDFs that are NOT on the whole very good quality wrt this. Difficult to know whether the authors or the publishers are to blame in each case but either way standards need to be improved.



By mining PDFs we can re-extract and re-release far more than just phylogenetic data from the literature - we're fairly sure we can reliably identify the rough type of figure depicted in PDFs by machine methods using certain diagnostic features such as number & proportion of horizontal and vertical lines.





Peter Murray-Rust & I now are **looking for a collaborator** to help us implement **machine learning methods** to classify scientific figures into discrete categories e.g. bar charts, scatter plots, network diagrams (including phylogenies), pie charts, box & whisker plots etc... in an automated way.

If you're interested please contact myself or Peter.


That's all for now.


PS If you're watching the London 2012 Olympics Volleyball tomorrow morning you may well just see me in the crowd. Managed to snaffle some returned tickets by setting up an alert for new tickets using a combination of www.page2rss.com (to alert me to page changes on the ticket website) and http://ifttt.com/ to email me as soon as the RSS feed gets a new item (updated ticket information). Without this nifty trick I very much doubt I'd have got any tickets. 
