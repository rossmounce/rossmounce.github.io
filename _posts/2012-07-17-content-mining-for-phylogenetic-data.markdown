---
author: rmounce
comments: true
date: 2012-07-17 14:58:46+00:00
layout: post
link: http://rossmounce.co.uk/2012/07/17/content-mining-for-phylogenetic-data/
slug: content-mining-for-phylogenetic-data
title: Content mining for phylogenetic data
wordpress_id: 287
categories:
- Content Mining
- Open Access
- Open Data
- Panton Fellowship updates
- Phylogenetics
---

I realise thus far, I may not have explained too clearly _exactly_ what I'm doing for my Panton fellowship. With this post I shall attempt to remedy this and shed a little more light on what I've been doing lately.

The main thrust of my fellowship is to extract phylogenetic tree data from the literature using [content mining](http://blog.okfn.org/2012/06/01/the-right-to-read-is-the-right-to-mine/) approaches (think text mining, but not just text!) - using the literature _in its entirety_ as my data. I have very little prior experience in this area, but luckily I have an expert mentor guiding me: [Peter](http://blogs.ch.cam.ac.uk/pmr/) [Murray-Rust](http://en.wikipedia.org/wiki/Peter_Murray-Rust) (whom you may often see referred to as PMR). For those of us biologists who may not be familiar with his work, whilst trying not to be too sycophantic about it, PMR is simply [brilliant](http://www-pmr.ch.cam.ac.uk/wiki/Publications), it's amazing what he and his collaborators have done to extract chemical data from the chemical literature and provide it openly for everyone, in spite of fierce opposition at times from those with vested interests in this data remaining 'closed'.

Now he's turned his attention to the biological literature for my project and together we're going to try and provide open tools to extract phylogenetic data from the literature. Initially I proposed trying to grab just tree topology and tip labels - a kind of bare minimum, but PMR has convinced me that we should be ambitious and all-encompassing, and thus our aims have expanded to include branch lengths, support values, the data-type the phylogeny was inferred from, and [other useful metadata](https://docs.google.com/document/d/1rFw-abx-oK8UVrnq4LYiVj1E2aNUI0dOEnlvbu88v9U/edit). And why not? We're ingesting the totality of the paper in our process, from title page to reference list, so there's plenty of machine-readable data to be gleaned. The question is, can we glean it off accurately enough, balancing precision and recall?

[![](http://rossmounce.co.uk/wp-content/uploads/2012/07/flow.png)](http://rossmounce.co.uk/wp-content/uploads/2012/07/flow.png)So for starters, we've been using test materials that we're legally allowed to, namely Open Access [CC-BY](http://creativecommons.org/licenses/by/3.0/) papers from BMC & PLoS to test our extraction tools, specifically focusing on a subset of all [~8500 papers](http://www.biomedcentral.com/search/results?drpAddedInLast=&txtSearch4=&txtSearch3=&portal_id=9001&txtSearch2=&txtSearch1=phylogen*&drpToDate=1997&excludePhrase1=&excludeField1=&search-button=Search&drpOrderBy=by+date&drpField1=%5BTW%5D&drpFromDate=2011&drpField3=%5BAU%5D&drpField2=%5BTI%5D&excludeSearchText1=&drpPhrase4=&drpEmailFormat=TEXT&drpPhrase3=&drpField4=&journalIssn=&drpPhrase2=&drpPhrase1=&itemsPerPage=100) containing the word-stem [phylogen* from BMC](http://www.citeulike.org/user/testtest87). It's a rough proxy for papers that'll contain a tree, and it's good enough for now - we'll need to be able to deal with false positives along with all the positive positives, so it's instructive to keep these in our sample.

We've been working on the regular structure of BMC PDFs, getting out bibliographic metadata, and the main-text for further NLP processing downstream to pick out data & method relevant words like say PAUP* , ML , mitochondrial loci etc... But the real reason we're deliberately using PDFs rather than the XML (which we also have access to) is the figures - where all the valuable phylogenetic tree data is. If this can be re-interpreted with reference to the bibliographic metadata, the figure caption and further methodological details from the full-text of the paper, then we may be able to reconstruct some fairly rich and useful phylogenetic data.




**[Liberating Our Beautiful Trees: A Call to Arms.](http://www.slideshare.net/hlapp/liberating-our-beautiful-trees-a-call-to-arms)** 


View more presentations from [Hilmar Lapp](http://www.slideshare.net/hlapp)





To make it clear, in slight contrast to the Lapp _et al_ iEvoBio presentation embedded above, we're not trying to _just_ extract the images, but rather to re-interpret them back into actual re-useable data, probably to be provided in [NeXML](http://www.nexml.org/) (and from there on, whatever form you want). We're pretty sure it's an achievable goal. Programs like [TreeThief](http://iubio.bio.indiana.edu/soft/iubionew/molbio/evolution/phylo/TreeThief/main.html), [TreeRipper](http://www.biomedcentral.com/1471-2105/12/178/abstract/), and [TreeSnatcher Plus](http://www.biomedcentral.com/1471-2105/13/110/abstract) have gone some way towards this already, but never before been incorporated in a content mining workflow AFAIK.

Unfortunately I wasn't at [iEvoBio](http://ievobio.org/) 2012 (I'm short on money and on time these days) but it's great to see from the slides the growing recognition of the [SVG](http://en.wikipedia.org/wiki/Scalable_Vector_Graphics) image file format as a brilliant tool for communicating digital science. I also put a bit about that in [my Hennig XXXI talk slides](http://prezi.com/xvas71fzr-am/hennig-xxxi/) too (towards the end). Programs like [TNT](http://www.zmuc.dk/public/phylogeny/tnt/) do output SVG files, so there's scope to make this a normal part of any publication workflow. Regrettably though, rather few publisher produced PDFs contain SVG formatted images - but if people, and editorial boards (perhaps?) can be made aware of their advantages, perhaps we can change this in future...?

[caption id="attachment_314" align="alignright" width="350"][![](http://rossmounce.co.uk/wp-content/uploads/2012/07/184212930-300x201.png)](http://rossmounce.co.uk/wp-content/uploads/2012/07/184212930.png) the very same file, opened as plain-text. It's fairly easy to reconvert back into re-useable machine-readable data.[/caption]



[caption id="attachment_312" align="alignleft" width="150"][![](http://rossmounce.co.uk/wp-content/uploads/2012/07/184213740-150x145.jpg)](http://rossmounce.co.uk/wp-content/uploads/2012/07/184213740.jpg) [Agapornis phylogeny.svg](http://en.wikipedia.org/wiki/File:Agapornis_phylogeny.svg) from Wikipedia (PD)[/caption]



















Gathering phylogenetic data from beyond PLoS, BMC and other smaller Open Access publishers is going to be hard, not for technical, but purely legal reasons:
[![](http://rossmounce.co.uk/wp-content/uploads/2012/07/chart.png)](http://rossmounce.co.uk/wp-content/uploads/2012/07/chart.png)


**The scope and scale of phylogenetic research (using 'phylogen*' as a proxy):**




There's a lot of phylogenetic research out there... but little of it is [Open Access](http://www.soros.org/openaccess/) - which is problematic for content mining approaches - particularly if subscription-access publishers are reticent to allow access.




Some facts:






	
  * with a Thomson Reuters Web of Science search, SCI-EXPANDED database (only), Topic=(phylogen*) AND Year Published=(2000-2011) this returns **101,669 results **(at the time of searching YMMV)

	
  * **91,788** of which are primary Research Articles (as opposed to Reviews, Proceedings Papers, Meeting Abstracts, Editorial Materials, Corrections, Book Reviews etc...)

	
  * Recent MIAPA working group research I contributed to (in review) quantitatively estimates that **approximately 66%** of papers containing 'phylogen*' report a new phylogenetic analysis (new data).

	
  * Thus conservatively assuming just one tree per paper (there are often many per paper), there are **> 60,000 trees** contained within just 21st century research articles. 

	
  * As with STM publishing as a whole, the number of phylogenetic research articles being published each year shows consistent year-on-year increases



	
  * Cross-match this with [publisher licencing data](https://docs.google.com/spreadsheet/ccc?key=0AtbO6mZEvieCdHBFa0dkTW5BYlMyRFZrUXhaNkZubEE#gid=0) and you'll find that **only ~11% of phylogenetic research published in 2010 was CC-BY Open Access** (and this % probably decreases as you go back before 2010)







So the real fun and games will come later this year, when I'm sure we'll have the _capability_ (software tools) to do some amazing stuff, having first perfected it on OA materials... [but will they let us](http://blogs.ch.cam.ac.uk/pmr/2012/07/01/understanding-diagrams-in-scientific-journals-i/)? Heather Piwowar's experience [earlier this year](http://researchremix.wordpress.com/2012/04/17/elsevier-agrees/) didn't look too fun - and that was all for just one publisher. Phylogenetic research occurs in and beyond at least 80 separate STM publishers by my count (let alone the >500 journals it occurs in!) - so there's no way anyone would bother trying to negotiate with them all! I'm sticking by the intuitive principle that [The Right to Read Is the Right to Mine](http://blog.okfn.org/2012/06/01/the-right-to-read-is-the-right-to-mine/) but I'll have a think about that some more when we actually get to that bridge.


Finally, it's also worth acknowledging that we're certainly not the first in this peculiar non-biomedical mining space - 'biodiversity informaticists' have been doing useful things with these techniques for a while now in innovative ways largely unrelated to medicine e.g. [LINNAEUS](http://linnaeus.sourceforge.net/) from [Casey Bergmann's lab](http://bergmanlab.smith.man.ac.uk/), and a recent review of other projects from [Thessen et al (2012)](http://dx.doi.org/10.1155/2012/391574) [hat-tip to [@rdmpage](https://twitter.com/rdmpage/) for bringing that later paper to the world's attention via Twitter]. Literally all areas of academia could probably benefit from some form or another of content mining - it's _not_ just a biomed / biochem tool.

So, I hope that explains things a bit better. Any questions?



**Some references (but not all!):**

Gerner, M., Nenadic, G., and Bergman, C. 2010. LINNAEUS: A species name identification system for biomedical literature. _BMC Bioinformatics_ 11:85+. [http://dx.doi.org/10.1186/1471-2105-11-85](http://dx.doi.org/10.1186/1471-2105-11-85) [CC-BY Open Access]

Thessen, A. E., Cui, H., and Mozzherin, D. 2012. Applications of natural language processing in biodiversity science. _Advances in Bioinformatics_ 2012:1-17. [http://dx.doi.org/10.1155/2012/391574](http://dx.doi.org/10.1155/2012/391574) [CC-BY Open Access]

Hughes, J. 2011. TreeRipper web application: towards a fully automated optical tree recognition software. _BMC Bioinformatics_ 12:178+. [http://dx.doi.org/10.1186/1471-2105-12-178](http://dx.doi.org/10.1186/1471-2105-12-178)  [CC-BY Open Access]

Laubach, T., von Haeseler, A., and Lercher, M. 2012. TreeSnatcher plus: capturing phylogenetic trees from images. BMC Bioinformatics 13:110+. [http://dx.doi.org/10.1186/1471-2105-13-110](http://dx.doi.org/10.1186/1471-2105-13-110) [CC-BY Open Access, incidentally I was one of the reviewers for this paper. I signed my review, and made a point of it too. Nor was it a soft review either I might add]
