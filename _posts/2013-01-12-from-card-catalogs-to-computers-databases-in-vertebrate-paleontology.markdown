---
author: rmounce
comments: true
date: 2013-01-12 18:19:23+00:00
layout: post
link: http://rossmounce.co.uk/2013/01/12/from-card-catalogs-to-computers-databases-in-vertebrate-paleontology/
slug: from-card-catalogs-to-computers-databases-in-vertebrate-paleontology
title: 'From card catalogs to computers: databases in vertebrate paleontology'
wordpress_id: 954
categories:
- Open Data
- Palaeontology
---

Anyone who knows me, knows I'm very passionate on the subject of data sharing in science, and after all the relevant conferences I've been to and research I've done - I don't mind saying I'm fairly knowledgeable on the subject too.

It's part of the reason I got this Panton Fellowship that has helped me develop my work and do what I want to do in pursuit of [Open Data](http://en.wikipedia.org/wiki/Open_data) goals.

So when I saw this article come up on my RSS feeds - I thought great! It's finally happening. The vertebrate palaeontology community is finally seeing the light - the _absolute need_ to share research data associated with published papers (we'll tackle pre-publication data sharing later, first things first...)!

`Uhen, M. D., Barnosky, A. D., Bills, B., Blois, J., Carrano, M. T., Carrasco, M. A., Erickson, G. M., Eronen, J. T., Fortelius, M., Graham, R. W., Grimm, E. C., O'Leary, M. A., Mast, A., Piel, W. H., Polly, P. D., and Säilä, L. K. 2013. 
[From card catalogs to computers: databases in vertebrate paleontology](http://dx.doi.org/10.1080/02724634.2012.716114). Journal of Vertebrate Paleontology 33:13-28.`

[![2013-01-12-142813_1054x983_scrot](http://farm9.staticflickr.com/8098/8373454790_bf101f3ab4.jpg)](http://www.flickr.com/photos/79472036@N07/8373454790/)

...and yet when I read the paper - it sorely disappointed me for a variety of reasons.


### Choosing examples: bad choices & odd absences


Despite clear criteria given, I found the choice of databases reviewed to be an odd selection - for example they choose to include AHOB ([Ancient Human Occupation of Britain](http://www.ahobproject.org/database/)) and write about it that:

"Access is restricted to project members during the life of the project, after which access will be publicly granted."

This probably explains why then, that when I go to the database website - **I can't seem to get access to any of the purported data to be there!**

[![AHOB](http://farm9.staticflickr.com/8237/8372441089_fbbe515d28.jpg)](http://www.flickr.com/photos/79472036@N07/8372441089/)
_Screenshot of the login screen for AHOB. [Try it yourself](http://www.ahobproject.org/database/)._

Yet apparently: "More than 250 publications have results from the AHOB project, all of which are recorded in the database."

How many more publications will come out of this cosy little database before access will be publicly granted I wonder? I don't think this is a good example of a research database as it doesn't seem to publicly share any data.


### Where's Dryad?


Furthermore there are some really big, obvious, relevant databases it neglects to review, in particular [Dryad](http://datadryad.org/) - the only mention of which is that TreeBASE received "some support from Dryad" - with absolutely no mention anywhere that Dryad itself is a database with [lots](http://dx.doi.org/10.5061/dryad.3t5s6) [of](http://dx.doi.org/10.5061/dryad.50r80407) [vertebrate palaeontological](http://dx.doi.org/10.5061/dryad.8961) [data](http://dx.doi.org/10.5061/dryad.25kd9) [in it](http://dx.doi.org/10.5061/dryad.4d5h8g12) and likely to be a strongly important, long-lasting database in this area for the foreseeable future IMO! Even some [data associated with an article in JVP](http://dx.doi.org/10.5061/dryad.93j174jd) itself is in Dryad! Although less prominently paleo-related [figshare](http://figshare.com/articles/search?q=category%3A+Paleontology&quick=1) (with no less that 26 paleontology-related datasets there at the moment, TreeBASE has approximately as many!) might have been worth mentioning too.

Dryad has a partnership with [The Paleontological Society](http://www.paleosoc.org/) and many evolutionary biology journals. Dryad even bought a promotional stand at last year's Society of Vertebrate Paleontology annual meeting (the society that publishes the Journal of Vertebrate Paleontology) but as Richard Butler has pointed out to me on Twitter this article was submitted before that meeting. Still, it's simply impossible that _none_ of the 16 authors listed doesn't know about Dryad. I find the non-inclusion of Dryad deeply suspicious and possibly political given it could 'compete' to store much of the data that some of the other reviewed databases do (it's a broad generalist in the types of data it accepts).

Isn't there a **conflict of interest** issue given that most of the authors of this paper are involved with at least one of the 'reviewed' (=advertised) databases in the paper? I see no mention of this conflict of interest anywhere in the paper. I dearly hope this paper was peer-reviewed - that it is an 'invited article' makes me wonder a bit about that...

The inclusion of [Polyglot Paleontologist](http://www.paleoglot.org/) too, in the reviewed databases does also rather stretch the meaning of 'data' in the word database. **Are translations of 434 different papers 'data'?** In the same way that TreeBASE or PaleoDB contain data? It's a fantastic freely provided resource, no doubt - I mean no criticism of it - but is it data? I think not tbh.


### Strong contenders for things that could/should have been cited but weren't


WRT to Data Portals: [rOpenSci](http://ropensci.org/) provide great [R](http://www.r-project.org/) interfaces for a wide variety of databases, including TreeBASE which was one of the 'reviewed' databases.

WRT to the History of databases section: I find it odd that they didn't think to mention my own [widely publicised](http://www.nature.com/news/2011/110411/full/472150a.html) and well-supported [call for data archiving in palaeontology](http://web.archive.org/web/20111223035621/http://supportpalaeodataarchiving.co.uk/) back in 2011. Nearly 200 palaeontologists signed in support of our ideas with some memorable quotes of support e.g. [Brian Huber](http://paleobiology.si.edu/staff/individuals/huber.html) "This is the way of the future" , [P J Wagner](http://paleobiology.si.edu/staff/individuals/wagner.html) "I've been trying to get the Paleo Society to sign on with Dryad, but it's been like slamming my head on jello..."

They could have explained why freely accessible databases/archives are so important a bit better in my opinion:
that '[Data archiving is a good investment](http://dx.doi.org/10.1038/473285a)' (Piwowar et al, 2012),
that [only 4% of phylogenetic data is currently archived and that it's really useful data](http://dx.doi.org/10.1186/1756-0500-5-574) (Stoltzfus et al, 2012),
that [Willingness to Share Research Data Is Related to the Strength of the Evidence and the Quality of Reporting of Statistical Results](http://www.plosone.org/article/info%3Adoi%2F10.1371%2Fjournal.pone.0026828) (Wicherts et al, 2011),
that the ["data available upon request" system really doesn't work](http://dx.doi.org/10.1037/0003-066X.61.7.726) (Wicherts et al, 2006)
the [undesirable consquences of non-commercial clauses applied to biodiversity data](http://dx.doi.org/10.3897/zookeys.150.2189) (Hagedorn et al, 2011)


### Odd wording


"...community approach, facilitated by the open access of the WWW and..."

sounds like something my dad would say about the interweb

"The CCL 3.0 license allows..."

a classic mistake - _which_ CCL license?
In this case they mean the Creative Commons Attribution-NonCommercial-ShareAlike 3.0 license, or CC BY-NC-SA for short. Calling it "Creative Commons License 3.0 (BY-NC-SA)" makes me wonder how familiar they are with licencing. Perhaps a sub-editor did this. And why they link specifically to the US version not the [international unported license](http://creativecommons.org/licenses/by-nc-sa/3.0/) I do not know.


### Data Citation: the Elephant in the Room?


Attribution is mentioned many times, and is vitally important to motivate people to share data. Yet the concept of _citing_ data in countable ways or [Data Citation](http://datacite.org/) isn't explicitly mentioned once. Nor [altmetrics](http://altmetrics.org/manifesto/) for that matter.

This would have been an excellent opportunity - the start of a new year to encourage authors to actually _cite_ data that they re-use from someone else so that those citations can be easily counted and contribute towards research evaluations, but alas no.


### So what now?


So I like some of the message of this paper. But I don't think it goes far enough, nor does a good job of it. Call me egotistical but I think I could do better and expand upon what I've written above.

If any journal editor happens to read this, and would like to commission an 'invited article', comment, or proper independent critical review of databases in vertebrate palaeontology / evolutionary biology please contact me. I think I could offer an interesting perspective.

PS I'm not going to write to the journal. I tried that with Nature and [it took 6 months from submission](http://rossmounce.co.uk/2011/08/11/my-1st-peer-review-published-paper/) for my comment to get [published](http://dx.doi.org/10.1038/nature10266)! It's 2013 - if I'm going to do [post-publication peer review](http://blogs.bmj.com/bmj/2011/04/06/richard-smith-what-is-post-publication-peer-review/) - I'll definitely be blogging it from now on, Rosie Redfield style!
