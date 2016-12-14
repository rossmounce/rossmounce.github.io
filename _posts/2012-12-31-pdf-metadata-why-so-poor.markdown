---
author: rmounce
comments: true
date: 2012-12-31 01:05:48+00:00
layout: post
link: http://rossmounce.co.uk/2012/12/31/pdf-metadata-why-so-poor/
slug: pdf-metadata-why-so-poor
title: PDF metadata - why so poor?
wordpress_id: 875
categories:
- Content Mining
- Open Data
- Panton Fellowship updates
tags:
- figshare
- FORCE11
- metadata
- pdf
- pdfs
- publishers
---

## Why is it so difficult to identify academic publisher PDFs?




With published MP3 files of _audio _you get rather good metadata. Take for example an MP3 file I downloaded from Hacker Public Radio available at the bottom of [this post](http://hackerpublicradio.org/eps.php?id=0874).

[![meta](http://farm9.staticflickr.com/8496/8326503334_a0108a0124.jpg)](http://www.flickr.com/photos/79472036@N07/8326503334/)



The Full Circle Magazine team _added value _to the content published by embedding clear and relevant metadata within the MP3 so that even years later, and renaming the file - I _still _know exactly what this file contains without the need to open/listen to it. The metadata standard for MP3 files is called [ID3](http://en.wikipedia.org/wiki/ID3). I haven't shown it but there's even a nice little _picture_ embedded as metadata. Rich, valuable metadata is a **good thing to have** and easy to provide.




## What then for PDF files?




They have embedded metadata too. On *nix machines you can use the CLI tool _[pdfinfo](http://linux.about.com/library/cmd/blcmdl1_pdfinfo.htm) _to show the metadata on your PDF files. I read that the metadata embedded in PDF is called [XMP](http://www.pdflib.com/knowledge-base/xmp-metadata/) (Adobe's Extensible Metadata Platform).

Is there an XMP standard / schema for published academic works in the PDF format? The only reason I ask is when I look at the Version of Record (VoR) files from many different publishers - the metadata I find is so variable in quality! No wonder [Mendeley](http://www.mendeley.com/) has difficulty identifying all the PDFs I feed it.

Below are results from a little preliminary survey of academic publisher PDF metadata I've done, with the supporting data uploaded to [figshare here](http://dx.doi.org/10.6084/m9.figshare.105633) if you're interested...

**Sample population:**  21 different academic publishers, ~3 Version of Record PDFs per publisher, mostly all published in the year 2011.



	
  * AAAS (Science), Wiley-Blackwell, BRILL, BMJ, Cambridge Journals Online, CSIRO, Elsevier, Frontiers In, Hindawi, Polish Academy of Sciences, Magnolia Press, National Academy of Sciences (PNAS), NPG, NRC Research Press, Pensoft Publishers, PLOS, Royal Society, SAGE, Senckenberg Natural History Collections Dresden, Springer-Verlag, Taylor & Francis, Sociedade Brasileira de Ictiologia (Neotropical Ichthyology)


You'll notice I'm mixing large publishers (Elsevier, Wiley, Springer...) with tiny society/institution published PDFs. Open Access and Toll Access (TA) publishers both represented. The results are rather interesting...

I gathered data on 11 metadata fields:
<table cellspacing="0" border="0" >
<tbody >
<tr >

<td align="LEFT" height="16" >**PDF Version**
</td>

<td align="LEFT" >**Optimized?**
</td>

<td align="LEFT" >**File Size (bytes)**
</td>

<td align="LEFT" >**Page Size**
</td>

<td align="LEFT" >**Producer**
</td>

<td align="LEFT" >**Creator**
</td>

<td align="LEFT" >**Title**
</td>

<td align="LEFT" >**Subject**
</td>

<td align="LEFT" >**Author**
</td>

<td align="LEFT" >**Pages**
</td>

<td align="LEFT" >**Keywords**
</td>
</tr>
</tbody>
</table>



##  Results


The results are very very ragbag. Out of the 70 PDFs I've published (meta)data on over at [Figshare](http://dx.doi.org/10.6084/m9.figshare.105633), only 8 of them had **Keywords** metadata embedded in them. So take a bow _Arthropod Systematics & Phylogeny_, _Frontiers in Neuroscience_, and _Geological Magazine _(Cambridge Journals Online) for those.

55% of them were not **Optimized**. Among those not_ _optimized were _Science _(AAAS), _Insect Systematics & Evolution _(BRILL), _Psyche_ (Hindawi), _Acta Palaeontologica Polonica_, _Proceedings of the National Academy of Sciences_, _Zookeys_ (Pensoft) and more. Hard to say whether PDF optimization is a good thing or not, depends on your POV I suppose. If anyone has any strong preferences either way please do comment.

**PDF version**: rare praise for Elsevier here - they appear to be one of only two publishers (SAGE the other) I've sampled here that actually publishes PDFs according to the latest standard (1.7), which incidentally has [been around since 2008](http://en.wikipedia.org/wiki/Portable_Document_Format#PDF_1.7)! I'm no PDF guru though, so I don't know if this actually entails any benefits or if there's much difference between the different standards. The average joe probably wouldn't notice the difference.

[![chart](http://farm9.staticflickr.com/8214/8327035299_a15fab321b.jpg)](http://www.flickr.com/photos/79472036@N07/8327035299/)

Curiously although two of the sampled Royal Society year-2011-published PDFs were version 1.4, a third one was a version 1.2 PDF - inconsistent and odd! Most PDFs (28) as the pie chart shows were version 1.4



**Page size **is entertainingly variable too: _Geological Magazine, __Acta Palaeontologica Polonica_, _Proceedings of the Royal Society B: Biological Sciences_, _Zootaxa, _and _Arthropod Systematics & Phylogeny _all go for 595 x 842 pts (A4).  _Science_, _Journal of Vertebrate Paleontology _and _Canadian Journal of Earth Sciences _use 612 x 792 pts (letter). The rest use an odd variety of sizes. Pensoft's choice of 467.717 x 680.315 pts looks small in comparison to the rest, I wonder what the rationale behind that choice was?

**Author: **Only just >50% of the sampled PDFs embedded author metadata. _Geological Magazine, Invertebrate Systematics_, _Zootaxa, Arthropod Systematics & Phylogeny _and_ Systematics and Biodiversity_ can all take credit for supplying full author data for each and every author on the author list of each PDF.

Others like _Nature_, _Molecular Phylogenetics and Evolution_ (Elsevier), _Frontiers in Neuroscience_, and _Psyche_ (Hindawi)_ _only acknowledge the first author of each PDF. The latter at least has the decency to acknowledge this with an embedded "{et al.}".

**Title: **Only _Cladistics_, _Geological Magazine, Invertebrate Systematics_, _Frontiers in Neuroscience_, _Zootaxa, Nature, _and_ Arthropod Systematics & Phylogeny _properly filled in this field.

**Subject: **bit of an odd field this one. Some publishers put the title of the journal in this field e.g. _Psyche_ (Hindawi) and _Nature_ (NPG). Whilst most of the others sampled had no metadata for this field, _Frontiers in Neuroscience _interestingly used this field for the first sentence of the abstract!

**Creator:  **

data given here and in the next metadata item (Producer) shines light on how these PDFs were created.

Values extracted included:

"Arbortext Advanced Print Publisher 9.0.114/W"
"Arbortext Advanced Print Publisher 9.1.510/W Unicode"
"3B2 Total Publishing System 7.51n/W"
"3B2 Total Publishing System 8.07j/W"
"dvips(k) 5.95a Copyright 2005 Radical Eye Software"    _Geological Magazine_
"Elsevier" _no surprises for guessing the publisher of this..._
"Adobe InDesign CS5 (7.0.4)"
"Adobe InDesign CS4 (6.0)" _SAGE_
"LaTeX with hyperref package" _Hindawi_
"FrameMaker 8.0" _Zootaxa_
"Adobe PageMaker 7.0" _Neotropical Ichthyology_

**Producer**

Values extracted include:

"Adobe PDF Library 9.0.1"
"Adobe PDF Library 9.9"
"PDFlib PLOP 2.0.0p6 (SunOS)/Acrobat Distiller 7.0 (Windows)" _Cladistics_
"iText 2.1.7 by 1T3XT"
"iText 2.1.5 (by lowagie.com)"
"Acrobat Distiller 6.0.1 (Windows)" _Nature_
"Acrobat Distiller 7.0 (Windows)" _Invertebrate Systematics_
"Acrobat Distiller 8.1.0 (Windows)" _Elsevier_
"Acrobat Distiller 9.3.3 (Windows)" _Canadian Journal of Earth Sciences_

It's interesting that _Nature_ in 2011 were using the oldest version of Acrobat Distiller, it's perhaps understandable that they value stability over updates. In both Producer and Creator metadata it seems like NRC Research Press (as represented by _Canadian Journal of Earth Sciences_) had the 'newest' most bleeding-edge PDF software setup in 2011.


## 




## Discussion




Clearly as with MP3's there's a need for good rich metadata to identify all the millions of different files out there. Publishers _could _provide this and as I've shown some do.



	
  * If there are agreed upon standards in STM publishing what are they?

	
  * Is there any agreed metadata standard for STM published PDFs? If not I think there should be.


I for one would like richer metadata in 2013 so that PDFs can be more easily identified in a machine-readable way - not even Mendeley can cope with all the PDFs I throw at it - my library is a mess.

Given we live in an increasingly mixed world of Open Access and Closed Access publications with content mining applications on the rise, it seems obvious that in particular these PDFs need a **Copyright **and/or licencing metadata field (as there is in MP3 metadata), to help indicate clearly what can and cannot be done with each PDF.

Please publishers, sort it out!



Happy New Year everyone...
