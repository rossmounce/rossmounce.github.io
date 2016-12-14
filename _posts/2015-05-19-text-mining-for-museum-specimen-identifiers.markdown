---
author: rmounce
comments: true
date: 2015-05-19 09:01:49+00:00
layout: post
link: http://rossmounce.co.uk/2015/05/19/text-mining-for-museum-specimen-identifiers/
slug: text-mining-for-museum-specimen-identifiers
title: Text mining for museum specimen identifiers
wordpress_id: 1802
categories:
- Content Mining
tags:
- Museum Identifiers
---

Now I'm at the Natural History Museum, London I've started a new and ambitious text-mining project: to find, extract, publish, and link-up all mentions of NHM, London specimens published in the recent research literature (born digital, published post-2000).

Rod Page is already blazing a trail in this area with older [BHL](http://www.biodiversitylibrary.org/) literature. See: [Linking specimen codes to GBIF](http://iphylo.blogspot.co.uk/2015/04/linking-specimen-codes-to-gbif.html) & [Design Notes on Modelling Links](http://iphylo.blogspot.co.uk/2014/08/some-design-notes-on-modelling-links.html) for recent, relevant posts. But there's still lots to be done I think, so here's my modest effort.



**Why?**

It's important to demonstrate the value of biological specimen collections. A lot of money is spent cataloguing, curating and keeping safe these specimens. It would be extremely useful to show that these specimens are being used, at scale, in real, recent research -- it's not just irrelevant stamp collecting.

Sometimes the [NHM, London specimen catalogue](http://data.nhm.ac.uk/dataset/collection-specimens) has incorrect, incomplete or outdated data about it's own specimens - there is better, newer data about them in the published literature that needs to be fed back to the museum.

An example: specimen "[BMNH 2013.2.13.3](http://data.nhm.ac.uk/specimen/7273484d-bb71-4452-a5a0-1685bc67c1c9)" is listed in the online catalogue on the NHM open data portal as _Petrochromis_ nov. sp. By searching the literature for BMNH specimens, I happened to find where the new species of this specimen was described: [http://dx.doi.org/10.1007/s10228-014-0396-9](http://dx.doi.org/10.1007/s10228-014-0396-9) as _Petrochromis horii_ Takahashi & Koblmüller, 2014. It's also worth noting this specimen has associated nucleotide sequence data on GenBank here: [http://www.ncbi.nlm.nih.gov/nuccore/AB850677.1](http://www.ncbi.nlm.nih.gov/nuccore/AB850677.1) .

Having talked a lot about the [5 stars of open data](http://5stardata.info/) in the context of research data recently, I wonder... wouldn't it be really useful to make 4 or 5 star linked open data around biological specimens? From Rod Page, I gather this is part of the grand goal of creating a biodiversity [knowledge graph](http://iphylo.blogspot.co.uk/search/label/Knowledge%20Graph).

For this project, I will be focussing on linking BMNH (NHM, London) specimen identifiers with publication identifiers (e.g. DOIs) and GenBank accession numbers.



**What questions to ask?**


Where have NHM, London specimens been used/published? What are the most used NHM, London specimens in research? How does NHM, London specimen usage compare to other major museums such as the [AMNH](http://www.amnh.org/) (New York) or [MNHN](https://www.mnhn.fr/) (Paris).




**Materials for Mining**


1.) The [PubMedCentral Open Access](http://www.ncbi.nlm.nih.gov/pmc/tools/openftlist/) subset – a million papers, but mainly biomedical research.
2.) Open Access & free access journals that not included in PMC
3.) [figshare](http://figshare.com/) – particularly useful if nothing else, as a means of mining PLOS ONE supplementary materials (I read recently that essentially 90% of figshare is actually PLOS ONE supp. material! See [Table 2](http://arxiv.org/abs/1503.01298))
4.) select subscription access journals – annoyingly hard to get access to in bulk, but important to include as sadly much natural history research is still published behind paywalls.



**(very) Preliminary Results**

The PMC OA subset is fantastic & really facilitates this kind of research - I wish ALL of the biodiversity literature was aggregated like (some) of the open access biomedical literature is. You can literally just download a million papers, click, and go do your research. It facilitates _rigorous_ research by allowing full machine access to full texts.

Simple grep searches for 'NHMUK' & 'BMNH [A-Z0-9][0-9]', two of the commonest citation forms by which specimens may be cited reveal many thousands of possible specimen mentions in the PMC OA subset I must now look through to clean-up & link-up. In terms of journals, these 'hits' in the PMC OA subset come from (in no particular order): PLOS ONE, Parasites & Vectors, PeerJ, ZooKeys, Toxins, Zoo J Linn Soc, Parasite, Frontiers in Zoology, Ecology & Evolution, BMC Research Notes, Biology Letters, BMC Evolutionary Biology, Aquatic Biosystems, BMC Biology, Molecular Ecology, Journal of Insect Science, Nucleic Acids Research and more...!

specimen "BMNH 86.10.4.2" is a great example to lookup / link-up on the NHM Open Data Portal: [http://data.nhm.ac.uk/specimen/8559613e-f2a3-447c-aa1a-d476600d3293](http://data.nhm.ac.uk/specimen/8559613e-f2a3-447c-aa1a-d476600d3293) the catalogue record has 7 associated images openly available under [CC BY](https://creativecommons.org/licenses/by/4.0/), so I can liven up this post by including an image of the specimen (below)! I found this specimen used in a PLOS ONE paper: Walmsley et al. (2013) Why the Long Face? The Mechanics of Mandibular Symphysis Proportions in Crocodiles. doi: [10.1371/journal.pone.0053873](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0053873) (in the text caption for figure 1 to be precise).

[caption id="" align="alignnone" width="1500"]![](http://www.nhm.ac.uk/services/media-store/asset/dcd637df6533f359ff570c89afa5669085ba0d71/contents/preview) © The Trustees of the Natural History Museum, London. Licensed for reuse under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). [Source](http://www.nhm.ac.uk/emu-classes/class.EMuMedia.php?irn=158767&image=yes&width=1500&height=1000).[/caption]





**Questions Arising**

How to find and extract mentions of NHM, London specimens in papers published in _Science_, _Nature_ & _PNAS _? There are sure to be many! I'm assuming the last 15 years worth of research published in these journals will be difficult to scrape - they would be quite likely to block my IP address if I tried to. Furthermore, all the actual science is typically buried in supplementary file PDFs in these journals not in the 'main' short article. Will _Science_, _Nature_ & _PNAS_  let me download all their supp material from the last 15 years? Is this facilitated at all? How do people actually do rigorous research when the contents of supplementary data files published in these journals are so undiscoverable & inaccessible to search?



It's clear to me there are many separate divisions when it comes to discoverability of research. There's the divide between open access (highly discoverable & searchable) and subscription access ([less discoverable](https://peerj.com/preprints/773/), less searchable, depending upon publisher-restrictions). There's also the divide between the 'paper' (more searchable) and 'supplementary materials' (less easily searchable). Finally, there's also the divide between textual and non-textual media: a huge amount of knowledge in the scientific literature is trapped in non-textual forms such as figure images which simply aren't instantly searchable by textual methods (figure captions DO NOT contain all of the information of the figure image! Also, OCR is time consuming and error-prone especially on the heterogeneity of fonts and orientation of words in most figures). For example, looking across thousands of papers with phylogenetic analyses published in the journal [IJSEM](http://ijs.sgmjournals.org/), 95% of the taxa / GenBank accessions used in them are _only_ mentioned in the figure image, nowhere else in the paper or supplementary materials as text! This needs to change.



As should be obvious by now; this is a very preliminary post, just to let people know what I'm doing and what I'm thinking. In my next post I'll detail some of the _subscription access_ journals I've been text mining for specimens, and the barriers I've encountered when trying to do so.



**Bonus question: How should I publish this annotation data?**

Easiest would be to release all annotations as a .csv on the NHM open data portal with 3 columns where each column mimics 'subject'  'predicate' 'object' notation: Specimen, "is mentioned in", Article DOI.

But if I wanted to publish something a little better & a little more formal, what kind of RDF vocabulary can I use to describe "occurs in" or "is mentioned in". What would be the most useful format to publish this data in so that it can be re-used and extended to become part of the biodiversity knowledge graph and have lasting value?
