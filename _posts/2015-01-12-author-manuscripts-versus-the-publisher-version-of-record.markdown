---
author: rmounce
comments: true
date: 2015-01-12 16:02:22+00:00
layout: post
link: http://rossmounce.co.uk/2015/01/12/author-manuscripts-versus-the-publisher-version-of-record/
slug: author-manuscripts-versus-the-publisher-version-of-record
title: Author manuscripts versus the publisher version of record
wordpress_id: 1590
categories:
- Content Mining
- Open Access
- Open Science
---

_[Update: I've submitted this idea as a [FORCE11 £1K Challenge research proposal](https://www.force11.org/node/6210) 2015-01-13. I may be unemployed from April 2015 onwards (unsolicited job offers welcome!), so I certainly might find myself with plenty of time on my hands to properly get this done...!]_

Inspired by something I heard [Stephen Curry](http://occamstypewriter.org/scurry/) say recently, and with a little bit of help from [Jo McIntyre](http://www.ebi.ac.uk/about/people/johanna-mcentyre) I've started a project to compare [EuropePMC](http://europepmc.org/) author manuscripts with their publisher-made (mangled?) 'version of record' twins.

How different are author manuscripts from the publisher version of record? Or put it another way, what value do publishers add to each manuscript? With the aggregation & linkage provided by EuropePMC - an excellent service - we can rigorously test this.



In this blog post I'll go through one paper I chose at random from EuropePMC:

_Sinha, N., Manohar, S., and Husain, M. 2013. Impulsivity and apathy in parkinson's disease. J Neuropsychol 7:255-283._  doi: [10.1111/jnp.12013](http://dx.doi.org/10.1111/jnp.12013) (publisher version) PMCID: [PMC3836240](http://europepmc.org/articles/PMC3836240) (EuropePMC version)

**Method**

A quick & dirty analysis with a simple tool that's easy to use & available to everyone:

_[pdftotext](http://en.wikipedia.org/wiki/Pdftotext) -layout     _(you're welcome to suggest a better method by the way, I like hacking PDFs)

**(P)** = Publisher-version , **(A)** = Author-version

Manual Post-processing - remove the header and footer crud from each e.g. "262
Nihal Sinha et al." **(P)** and "J Neuropsychol. Author manuscript; available in PMC 2013 November 21." **(A)**

Automatic Post-processing - I'm not interested in numbers or punctuation or words of 3-letters or less so I applied this bash-one-liner:

_strings **$inputfile** | tr '[A-Z]' '[a-z]' | sed 's/[[:punct:]]/ /g' | sed 's/[[:digit:]]/ /g' |  sed s/' '/\\n/g | awk 'length > 3' | sort | uniq -c | sort -nr > **$outputfile**_

Then I just manually diff'd the resulting word lists - there's so little difference it's easy for this particular pair.



**Results**

The correspondence line changed slightly from this in the author version:

Correspondence should be addressed to Nuffield Department of Clinical Neurosciences and Department Experimental Psychology, Oxford University, Oxford OX3 9DU, UK (masud.husain@ndcn.ox.ac.uk). . **(A)**

To this in the publisher version (I've added bold-face to highlight the changes):

Correspondence should be addressed to **Masud Husain**, Nuffield Department of Clinical Neurosciences and Department Experimental Psychology, Oxford University, Oxford OX3 9DU, UK (**e-mail:** masud.husain@ndcn.ox.ac.uk). **(P)**



Reference styling has been changed. Why I don't know, seems a completely pointless change. Either style seems perfectly functional to me tbh:

Drijgers RL, Dujardin K, Reijnders JSAM, Defebvre L, Leentjens AFG. Validation of diagnostic criteria for apathy in Parkinson’s disease. Parkinsonism & Related Disorders. 2010; 16:656–660. doi:10.1016/j.parkreldis.2010.08.015. [PubMed: 20864380] **(A)**

to this in the publisher version:

Drijgers, R. L., Dujardin, K., Reijnders, J. S. A. M., Defebvre, L., & Leentjens, A. F. G. (2010). Validation of diagnostic criteria for apathy in Parkinson’s disease. _Parkinsonism & Related Disorders_, 16, 656–660. doi:10.1016/j.parkreldis.2010.08.015 **(P)**

In the publisher-version only **(P)** "Continued" has been added below some tables to acknowledge that they overflow on the next page. Arguably the publisher has made the tables worse as they've put them sideways (landscape) so they now overflow onto other pages. In the author-version **(A)** they are portrait-orientated and so hence each fit on one page entirely.



Finally, and most intriguingly, some of the figure-text comes out only in the publisher-version **(P)**. In the author-version **(A) **the figure text is entirely image pixels, not copyable text. Yet the publisher version has introduced some clearly imperfect figure text. Look closely and you'll see in some places e.g. "Dyskinetic state" of figure 2 c) in **(P)**, the 'ti' has been [ligatured](http://en.wikipedia.org/wiki/Typographic_ligature) and is copied out as a theta symbol:

DyskineƟc state



**Discussion**



I don't know about you, but for this particular article, it doesn't seem like the publisher has really done all that much aside from add their own header & footer material, some copyright stamps & their journal logo - oh, and 'organizing peer-review'. How much do we pay academic publishers for these services? Billions? Is it worth it?

I plan to sample at least 100 'twinned' manuscript-copies and see what the average difference is between author-manuscripts and publisher-versions. If the above is typical of most then this will be really bad news for the legacy academic journal publishers... Watch this space!



Thoughts or comments as to how to improve the method, or relevant papers to read on this subject are welcome. Collaboration welcome too - this is an activity that scales well between collaborators.
