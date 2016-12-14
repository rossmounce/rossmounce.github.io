---
author: rmounce
comments: true
date: 2013-07-09 12:13:36+00:00
layout: post
link: http://rossmounce.co.uk/2013/07/09/hack4ac-recap/
slug: hack4ac-recap
title: Hack4ac recap
wordpress_id: 1219
categories:
- BMC
- eLife
- Hack days
- Open Access
- Open Data
- Open Science
- PeerJ
- PLoS
---

Last Saturday I went to [Hack4Ac](http://hack4ac.com/) - a hackday in London bringing together many sections of the academic community in pursuit of two goals:



	
  * To demonstrate the value of the CC-BY licence within academia. We are interested in supporting innovations around and on top of the literature.

	
  * To reach out to academics who are keen to learn or improve their programming skills to better their research. We’re especially interested in academics who have never coded before




[![DSCF3425](http://farm6.staticflickr.com/5324/9243272700_389020ff92.jpg)](http://www.flickr.com/photos/mulvanynet/9243272700/)


The list of [attendees](http://hack4ac.eventbrite.co.uk/?ref=ecount) was stellar, cross-disciplinary (inc. Humanities) and international. The venue ([Skills Matter](http://skillsmatter.com/)) & organisation were also suitably first-class - lots of power leads, spare computer mice, projectors, whiteboards, good wi-fi, separate workspaces for the different self-assembled hack teams, tea, coffee & snacks all throughout the day to keep us going, prizes & promo swag for all participants...

The principal organizers; [Jason Hoyt](https://peerj.com/about/#jason-hoyt) (PeerJ, [formerly at Mendeley](http://enjoythedisruption.com/post/47527556151/my-thoughts-on-mendeley-elsevier-why-i-left-to-start)) & Ian Mulvany ([Head of Tech](http://www.elifesciences.org/about/elife-community/executive-staff/ian-mulvany-head-of-technology/) at eLife) thus deserve a BIG thank you for making all this happen. I hear this may also be turned into a fairly regular set of meetups too, which will be great for keeping up the momentum of innovation going on right now in academic publishing.


## The hack projects themselves...


The overall winner of the day was [ScienceGist](http://www.sciencegist.com/) as voted for by the attendees. All the projects were great in their own way considering we only had from ~10am to 5pm to get them in a presentable state.

[![ScienceGist](http://farm3.staticflickr.com/2861/9244636597_6e822ed24b.jpg)](http://www.flickr.com/photos/79472036@N07/9244636597/)



This project was initiated by [Jure Triglav](http://www.juretriglav.si/about/), building upon his previous experience with [Tiris](http://www.tiris.org/). This new project aims to provide an open platform for post-publication summaries ('gists') of research papers, providing shorter, more easily understandable summaries of the content of each paper.

I also led a project under the catchy-title of **Figures → Data** where-by we tried to provide added-value by taking CC-BY bar charts and histograms from the literature and attempting to re-extract the numerical data from those plots with automated efforts using computer vision techniques. On my team for the day I had [Peter Murray-Rust](http://en.wikipedia.org/wiki/Peter_Murray-Rust), [Vincent Adam](https://twitter.com/vincentadam87) (of [HackYourPhD](http://hackyourphd.org/)) and [Thomas Branch](http://www3.imperial.ac.uk/chemicalbiology/doctoraltrainingcentre/icbstudents/mreschemicalbiology1011/branch) (Imperial College). This was handy because I know next to nothing about [computer vision](http://en.wikipedia.org/wiki/Computer_vision) - I'm Your Typical Biologist ™  in that I know how to script in R, perl, bash and various other things, just enough to get by but not nearly enough to attempt something ambitious like this on my own!

Forgive me the self-indulgence if I talk about this  **Figures → Data **project more than I do the others but I thought it would be illuminative to discuss the whole process in detail...

In order to share links between our computers in real-time, and to share initial ideas and approaches, Vincent set-up an etherpad [here](http://beta.etherpad.org/p/hack4ac_figures_to_data) to record our notes. You can see the development of our collaborative note-taking using the timeslider function below (I did a screen record of it for prosperity using [recordmydesktop](http://recordmydesktop.sourceforge.net/about.php)):



In this etherpad we document that there are a variety of ways in which to discover bar charts & histograms:



	
  * [figuresearch](http://figuresearch.askhermes.org/integrated/FigureSearch.uwm) is one such web-app that searches the PMC OA subset for figure captions & figure images. With this you can find over 7,000 figure captions containing the word 'histogram' (you would assume that the corresponding figure would contain at least one histogram for 99% of those figures, although there are [exceptions](http://figuresearch.askhermes.org/integrated/ShowArticle.uwm?articleid=4355522&searchterm=histogram&figureid=16025186)).

	
  * [figshare](http://figshare.com/articles/search?q=histogram&figure=on&lsort=recent&ltype=articles&start=&end=) has nearly 10,000 hits for histogram figures, whilst BMC & PLOS can also be commended for providing the ability to search their literature stack by _just_ figure captions, making the task of figure discovery far more efficient and targeted.


Jason Hoyt was in the room with us for quite a bit of the hack and clearly noted the search features we were looking for - just yesterday he tweeted: "PeerJ now supports figure search & all images free to use CC-BY (inspired by [@rmounce](http://twitter.com/rmounce) at [#hack4ac](http://twitter.com/search?q=%23hack4ac))" [[link](https://twitter.com/thePeerJ/status/354323740751970304)] - I'm really glad to see our hack goals helped Jason to improve content search for PeerJ to better enable the needs (albeit somewhat niche in this case) of _real_ researchers. It's this kind of unique confluence of typesetters, publishers, researchers, policymakers and hackers at _doing_-events like this that can generate real change in academic publishing.

The downside of our project was that we discovered someone's done much of this before. _[ReVision: Automated Classification, Analysis and Redesign of Chart Images](http://vis.stanford.edu/files/2011-ReVision-UIST.pdf)  _[PDF] was an award-winning paper at an ACM conference in 2011. Much of this project would have helped our idea, particularly the classification of figures tech. Yet sadly, as with so much of 'closed' science we couldn't find _any_ open source code associated with this project. There were comments that this type of non-code sharing behaviour, blocking re-use and progress, are fairly typical in computer science & ACM conferences (I wouldn't know but it was muttered...).  _If anyone does know of the existence of related open source code available for this project do let me know!_

So... we had to start from a fairly low-level ourselves: Vincent & Thomas tried MATLAB & C based approaches with [OpenCV](http://opencv.org/) and their code is all up on our project github. Peter tried using [AMI2 toolset](https://bitbucket.org/petermr/ami2), particularly the [Canny algorithm](http://en.wikipedia.org/wiki/Canny_edge_detector), whilst I built up an annotated corpus of 40 CC-BY bar charts & histograms for testing purposes. Results of all three approaches can be seen below in their attempts to simplify this hilarious figure about dolphin cognition from a PLOS paper:

[caption id="" align="aligncenter" width="600"][![The plastic fish just wasn't as captivating...](http://www.plosone.org/article/fetchObject.action?uri=info:doi/10.1371/journal.pone.0030001.g005&representation=PNG_M)](http://www.plosone.org/article/info%3Adoi%2F10.1371%2Fjournal.pone.0030001) "Figure 5. Total time spent looking at different targets." from Siniscalchi M, Dimatteo S, Pepe AM, Sasso R, Quaranta A (2012) [Visual Lateralization in Wild Striped Dolphins (Stenella coeruleoalba) in Response to Stimuli with Different Degrees of Familiarity](http://www.plosone.org/article/info%3Adoi%2F10.1371%2Fjournal.pone.0030001). PLoS ONE 7(1): e30001. doi:10.1371/journal.pone.0030001 CC-BY[/caption]

[Peter's results](https://github.com/rossmounce/hack4ac-figures/blob/master/images/pmrCanny/journal.pone.0030001.g005.png.png) (using AMI2):

[![](http://rossmounce.co.uk/wp-content/uploads/2013/07/journal.pone_.0030001.g005.png-300x172.png)](http://rossmounce.co.uk/wp-content/uploads/2013/07/journal.pone_.0030001.g005.png.png)



[Thomas's results](https://github.com/rossmounce/hack4ac-figures/blob/master/code/screenshots/fig2.png) (OpenCV & C):

![](https://github.com/rossmounce/hack4ac-figures/blob/master/code/screenshots/fig2.png?raw=true)



[Vincent's results](https://github.com/rossmounce/hack4ac-figures/blob/master/code_vincent/res1.png) (OpenCV & MATLAB & [bilateral filtering](http://en.wikipedia.org/wiki/Bilateral_filter))

![](https://github.com/rossmounce/hack4ac-figures/blob/master/code_vincent/res1.png?raw=true)

We might not have won 1st prize but I think our efforts are pretty cool, and we got some laughs from our slides presenting our days' work at the end (e.g. see below). Importantly, *everything* we did that day is openly-available [on github](https://github.com/rossmounce/hack4ac-figures/) to re-use, re-work and improve upon (I'll ping Thomas & Vincent soon to make sure their code contributions are openly licensed). Proper full-stack open science basically!

[![some figures are just awful](http://rossmounce.co.uk/wp-content/uploads/2013/07/awful-300x225.jpg)](http://rossmounce.co.uk/wp-content/uploads/2013/07/awful.jpg)




## Other hack projects...


As I thought would happen I've waffled on about our project. If you'd like to know more about the other projects hopefully someone else will blog about them at greater length (sorry!) I've got my thesis to write y'know! ;)

You can find more about them all either on the Twitter channel [#hack4ac](https://twitter.com/search?q=%23hack4ac&src=typd) or alternatively on the [hack4ac github page](https://github.com/hack4ac). I'll write a little bit more below, but it'll be concise, I warn you!



	
  * **Textmining PLOS Author Contributions**


[caption id="" align="aligncenter" width="600"]![](https://pbs.twimg.com/media/BOgKsFvCAAE_C3z.jpg) [Photo tweeted by @protohedgehog](https://twitter.com/Protohedgehog/status/353544323314352130)[/caption]

This project has a lovely website for itself: [http://hack4ac.com/plos-author-contributions/](http://hack4ac.com/plos-author-contributions/) and so needs no more explanation.



	
  * **Getting more openly-licensed content on wikipedia**


This group had problems with the YouTube API I think. Ask [@EvoMRI](https://twitter.com/EvoMRI) (Daniel Mietchen) if you're interested...



	
  * **articlEnhancer**


Not content with helping out the PLOS author contribs project Walther Georg also unveiled his own article enhancer project which has a nice webpage about it here: [http://waltherg.github.io/articlEnhancer/](http://waltherg.github.io/articlEnhancer/)



	
  * **Qual or Quant methods?**


[Dan Stowell](https://twitter.com/mclduk) & co used NLP techniques on full-text accessible CC-BY research papers, to classify all of them in an automated way determining whether they were qualitative or quantitative papers (or a mixture of the two). The last tweeted report of it sounded rather promising: "Upstairs at [#hack4ac](https://twitter.com/search?q=%23hack4ac&src=hash) we're hacking a system to classify research papers as qual or quant. first results: 96 right of 97. [#woo](https://twitter.com/search?q=%23woo&src=hash) [#NLPwhysure](https://twitter.com/search?q=%23NLPwhysure&src=hash)" More generally, I believe their idea was to enable a "search by methods" capability, which I think would be highly sought-after if they could do it. Best of luck!
Apologies if I missed any projects. Feel free to post epic-long comments about them below ;)






