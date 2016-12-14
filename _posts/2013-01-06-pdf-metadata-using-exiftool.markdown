---
author: rmounce
comments: true
date: 2013-01-06 21:14:10+00:00
layout: post
link: http://rossmounce.co.uk/2013/01/06/pdf-metadata-using-exiftool/
slug: pdf-metadata-using-exiftool
title: 'PDF metadata: different tool, same story'
wordpress_id: 926
categories:
- Content Mining
- Open Data
- Panton Fellowship updates
tags:
- FORCE11
---

So [a week ago](http://rossmounce.co.uk/2012/12/31/pdf-metadata-why-so-poor/), I investigated publisher-produced Version of Record PDFs with [_pdfinfo_](http://linux.about.com/library/cmd/blcmdl1_pdfinfo.htm) and the results were very disappointing. Lots of missing metadata was found and one could not reliably identify most of these PDFs from metadata alone, let alone extract particular fields of interest.

But [Rod Page](https://twitter.com/rdmpage) kindly alerted to me the fact that I might be using the wrong tool for this investigation. So at his suggestion I've tried again to extract metadata from the exact same set of PDFs as last time...

Only this time I'll be using [exiftool](http://www.sno.phy.queensu.ca/~phil/exiftool/) version 9.10.

[![](http://www.ediscoveryreadingroom.com/wp-content/uploads/2012/02/metadata.jpg)](http://www.ediscoveryreadingroom.com/wp-content/uploads/2012/02/metadata.jpg)This time I've put the full raw metadata output from exiftool [on figshare for each and every PDF](http://dx.doi.org/10.6084/m9.figshare.106195) file, just to _really_ prove the point, [reproducible research](http://en.wikipedia.org/wiki/Reproducibility#Reproducible_research) and all. I'd love to post the corresponding PDFs too but sadly many of them are not Open Access and this thus prevents me from uploading them to a public space.   **Insert timely comment here about how closed access publications stifle effective research practices...**

Exiftool is really simple to use. You just need type:
`exiftool NameOfPDF.pdf`
to get a human-readable exhaustive output of all possible metadata.

and
`exiftool -b -XMP NameOfPDF.pdf`
to get XML-structured metadata. I could only extract this from 56 of the 69 PDF files. The data output from this for those 56 PDFs is available as a separate fileset [on figshare here](http://dx.doi.org/10.6084/m9.figshare.106252).

Finally, if you want to test a whole bunch of PDF files in your working directory I've made a simple shell script that loops through all PDFs in your working directory, [available here](http://dx.doi.org/10.6084/m9.figshare.106194) (oops, it's not data, perhaps I should have put that on github instead?). [I'm sure many readers will be able to create a simple bash loop themselves but just for those that don't...]



I'm assuming that the reason `exiftool -b -XMP` failed on 13 of those PDFs is because they have no embedded XMP metadata - an empty (zero-byte sized) file is created for these. This is an assumption though... I notice that those 13 exactly correspond with all the 13 that were produced with [iText](http://itextpdf.com/). I checked the website and I'm pretty sure iText 2.x and up _can_ embed XMP metadata, it's just whether the publishers have bothered to use & apply this functionality.

So if I'm right, neither _Taylor & Francis_, _BRILL_, nor _Acta Palaeontology Polonica_ embed XMP metadata (at all!) in their PDFs. The alternative explanation is that the XMP metadata is in there but exiftool for whatever reason can't read/parse it from iText produced PDFs. I find this an unlikely alternative explanation though tbh.

Elsevier have superior XMP metadata to everyone else by the looks of it, but Elsevier aside the metadata is still very poor, so my conclusions from [last week's post](http://rossmounce.co.uk/2012/12/31/pdf-metadata-why-so-poor/) still stand I think.

Most of the others do contain metadata (of some sort) but by and large it's rather poor. I need to get some other work done on Monday so I'm afraid this is where I'm going to leave this for now. But I hope I've made the point.

**Further angles to explore**

Interestingly Brian Kelly, has taken this a slightly different direction and looked at the [metadata of PDFs in institutional repositories](http://ukwebfocus.wordpress.com/2013/01/04/embedded-metadata-in-pdfs-hosted-in-institutional-repositories-an-inside-out-outside-in-view/). I hadn't realised this but apparently some institutional repositories (IRs) universally add cover pages to most deposits. If this is done without care for the embedded metadata, the original metadata can be wiped and/or replaced with newer (less informative) metadata.  Not to mention that cover pages are completely unnecessary -> all the information on a cover page is exactly the kind of stuff that should be put in embedded metadata! No need to waste time and space by putting that info as the first page. [JSTOR](http://www.jstor.org/) does this too (cover pages) and it annoys the hell out of me.

After some excellent chat on Twitter about this IR angle I've discovered that UKOLN based here on campus at Bath have also done some interesting research in this area, in particular the [FixRep project](http://www.jisc.ac.uk/whatwedo/programmes/inf11/resdis/fixrep) which is described in more detail [here](http://blogs.ukoln.ac.uk/ukolndev/2010/11/17/extended-repository-pdf-assessment/). CrossRef labs [pdfmark](http://labs.crossref.org/pdfmark/pdfmark.html) tool also looks like something of interest towards fixing poor quality metadata PDFs. I've got this installed/compiled from the [source on github](https://github.com/CrossRef/pdfmark) but haven't tried it out yet. It would be interesting to see the difference it makes - a before and after comparison of metadata to see what we're missing... But why should we fix a problem that shouldn't exist in the first place? Publishers are the point of origin for this. It's their _job_ to be the first to publish the Version of Record. They should provide the highest level of metadata possible IMO.



**Why would publishers add metadata?**

Because their customers - libraries, governments, research funders (in the case of Open Access PDFs ) should demand it. A pipe dream perhaps but that's my $.02.  I would ask for a refund if I downloaded MP3's from iTunes/Amazon MP3 with insufficient embedded metadata. Why not the same principle for electronically published PDFs?



PS Apologies for some of the very cryptic filenames in the metadata uploads on figshare. You'll have to cross-match with this list here or the spreadsheet I uploaded last week to work out which metadata file corresponds to which PDF/Bibliographic Data record/Publisher.
<table cellspacing="0" border="0" > 
<tbody >
<tr >

<td align="CENTER" height="20" >**Publisher**
</td>

<td align="CENTER" >**Identifier**
</td>

<td align="CENTER" >**Journal**
</td>

<td align="CENTER" >**Contains embedded XMP metadata?**
</td>

<td align="CENTER" >**Filename**
</td>
</tr>
<tr >

<td align="CENTER" height="19" >American Association for the Advancement of Science
</td>

<td align="CENTER" >Ezard2011
</td>

<td align="CENTER" >Science
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >ezard_11_interplay_759293.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >American Association for the Advancement of Science
</td>

<td align="CENTER" >Nagalingum2011
</td>

<td align="CENTER" >Science
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >nagalingum_11_recent_719133.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >American Association for the Advancement of Science
</td>

<td align="CENTER" >Rowe2011
</td>

<td align="CENTER" >Science
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >Science-2011-Rowe-955-7.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Blackwell Publishing Ltd
</td>

<td align="CENTER" >Burks2011
</td>

<td align="CENTER" >Cladistics
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >burks_11_combined_694888.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Blackwell Publishing Ltd
</td>

<td align="CENTER" >Janies2011
</td>

<td align="CENTER" >Cladistics
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >janies_11_supramap_779773.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Blackwell Publishing Ltd
</td>

<td align="CENTER" >Simmons2011
</td>

<td align="CENTER" >Cladistics
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >simmons_11_deterministic_779537.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >BRILL
</td>

<td align="CENTER" >Barbosa2011
</td>

<td align="CENTER" >Insect Systematics & Evolution
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >barbosa_11_phylogeny_779910.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >BRILL
</td>

<td align="CENTER" >Dellape2011
</td>

<td align="CENTER" >Insect Systematics & Evolution
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >dellape_11_phylogenetic_779909.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Cambridge Journals Online
</td>

<td align="CENTER" >Knoll2010
</td>

<td align="CENTER" >Geological Magazine
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >knoll_10_primitive_475553.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Cambridge Journals Online
</td>

<td align="CENTER" >Saucede2007
</td>

<td align="CENTER" >Geological Magazine
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >thomas_saucegraved_07_phylogeny_506869.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >CSIRO
</td>

<td align="CENTER" >Chamorro2011
</td>

<td align="CENTER" >Invertebrate Systematics
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >chamorro_11_phylogeny_780467.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >CSIRO
</td>

<td align="CENTER" >Daugeron2011
</td>

<td align="CENTER" >Invertebrate Systematics
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >daugeron_11_phylogenetic_780466.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >CSIRO
</td>

<td align="CENTER" >Johnson2011
</td>

<td align="CENTER" >Invertebrate Systematics
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >johnson_11_collaborative_750540.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Elsevier
</td>

<td align="CENTER" >Lane2011
</td>

<td align="CENTER" >Molecular Phylogenetics and Evolution
</td>

<td align="CENTER" >yes
</td>

<td align="CENTER" >E3-1-s2.0-S1055790311001448-main.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Elsevier
</td>

<td align="CENTER" >Cunha2011
</td>

<td align="CENTER" >Molecular Phylogenetics and Evolution
</td>

<td align="CENTER" >yes
</td>

<td align="CENTER" >E2-1-s2.0-S1055790311001680-main.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Elsevier
</td>

<td align="CENTER" >Spribille2011
</td>

<td align="CENTER" >Molecular Phylogenetics and Evolution
</td>

<td align="CENTER" >yes
</td>

<td align="CENTER" >E1-1-s2.0-S1055790311001606-main.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Frontiers In
</td>

<td align="CENTER" >Horn2011
</td>

<td align="CENTER" >Frontiers in Neuroscience
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >fnins-05-00088.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Frontiers In
</td>

<td align="CENTER" >Ogura2011
</td>

<td align="CENTER" >Frontiers in Neuroscience
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >fnins-05-00091.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Frontiers In
</td>

<td align="CENTER" >Tsagareli2011
</td>

<td align="CENTER" >Frontiers in Neuroscience
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >fnins-05-00092.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Hindawi
</td>

<td align="CENTER" >Diniz2012
</td>

<td align="CENTER" >Psyche: A Journal of Entomology
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >79139500.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Hindawi
</td>

<td align="CENTER" >Restrepo2012
</td>

<td align="CENTER" >Psyche: A Journal of Entomology
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >516419.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Hindawi
</td>

<td align="CENTER" >Savopoulou2012
</td>

<td align="CENTER" >Psyche: A Journal of Entomology
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >167420.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Institute of Paleobiology, Polish Academy of Sciences
</td>

<td align="CENTER" >Amson2011
</td>

<td align="CENTER" >Acta Palaeontologica Polonica
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >amson_11_affinities_666987.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Institute of Paleobiology, Polish Academy of Sciences
</td>

<td align="CENTER" >Edgecombe2011
</td>

<td align="CENTER" >Acta Palaeontologica Polonica
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >edgecombe_11_new_666988.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Institute of Paleobiology, Polish Academy of Sciences
</td>

<td align="CENTER" >Williamson2011
</td>

<td align="CENTER" >Acta Palaeontologica Polonica
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >app2E20092E0147.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Magnolia Press
</td>

<td align="CENTER" >Agiuar2011
</td>

<td align="CENTER" >Zootaxa
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >zt02846p098.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Magnolia Press
</td>

<td align="CENTER" >Ebach2011
</td>

<td align="CENTER" >Zootaxa
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >ebach_11_taxonomy_599972.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Magnolia Press
</td>

<td align="CENTER" >Nelson2011
</td>

<td align="CENTER" >Zootaxa
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >nelson_11_resemblance_688762.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >National Academy of Sciences
</td>

<td align="CENTER" >Casanovas2011
</td>

<td align="CENTER" >Proceedings of the National Academy of Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >casanovas-vilar_11_updated_644658.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >National Academy of Sciences
</td>

<td align="CENTER" >Goswami2011
</td>

<td align="CENTER" >Proceedings of the National Academy of Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >goswami_11_radiation_814757.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >National Academy of Sciences
</td>

<td align="CENTER" >Thorne2011
</td>

<td align="CENTER" >Proceedings of the National Academy of Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >thorne_11_resetting_654055.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Nature Publishing Group
</td>

<td align="CENTER" >Meng2011
</td>

<td align="CENTER" >Nature
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >meng_11_transitional_644647.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Nature Publishing Group
</td>

<td align="CENTER" >Rougier2011
</td>

<td align="CENTER" >Nature
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >rougier_11_highly_720202.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Nature Publishing Group
</td>

<td align="CENTER" >Venditti2011
</td>

<td align="CENTER" >Nature
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >venditti_11_multiple_779840.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >NRC Research Press
</td>

<td align="CENTER" >CruzadoCaballero2010
</td>

<td align="CENTER" >Canadian Journal of Earth Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >650000.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >NRC Research Press
</td>

<td align="CENTER" >Druckenmiller2010
</td>

<td align="CENTER" >Canadian Journal of Earth Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >80000000c5.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >NRC Research Press
</td>

<td align="CENTER" >Mazierski2010
</td>

<td align="CENTER" >Canadian Journal of Earth Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >mazierski_10_description_577223.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >NRC Research Press
</td>

<td align="CENTER" >Modesto2009
</td>

<td align="CENTER" >Canadian Journal of Earth Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >modesto_09_new_577201.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >NRC Research Press
</td>

<td align="CENTER" >Parsons2009
</td>

<td align="CENTER" >Canadian Journal of Earth Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >parsons_09_new_575744.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >NRC Research Press
</td>

<td align="CENTER" >Wu2007
</td>

<td align="CENTER" >Canadian Journal of Earth Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >wu_07_new_622125.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Pensoft Publishers
</td>

<td align="CENTER" >Hagedorn2011
</td>

<td align="CENTER" >ZooKeys
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >hagedorn_11_creative_779747.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Pensoft Publishers
</td>

<td align="CENTER" >Penev2011
</td>

<td align="CENTER" >ZooKeys
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >penev_11_interlinking_694886.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Pensoft Publishers
</td>

<td align="CENTER" >Thessen2011
</td>

<td align="CENTER" >ZooKeys
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >thessen_11_data_779746.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Public Library of Science
</td>

<td align="CENTER" >Hess2011
</td>

<td align="CENTER" >PLoS ONE
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >hess_11_addressing_694222.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Public Library of Science
</td>

<td align="CENTER" >McDonald2011
</td>

<td align="CENTER" >PLoS ONE
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >mcdonald_11_subadult_694229.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Public Library of Science
</td>

<td align="CENTER" >Wicherts2011
</td>

<td align="CENTER" >PLoS ONE
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >wicherts_11_willingness_779788.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >SAGE Publications
</td>

<td align="CENTER" >deKloet2011
</td>

<td align="CENTER" >Journal of Veterinary Diagnostic Investigation
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >Invest-2011-deKloet-421-9.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >SAGE Publications
</td>

<td align="CENTER" >Richter2011
</td>

<td align="CENTER" >Journal of Veterinary Diagnostic Investigation
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >Invest-2011-Richter-430-5.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >SAGE Publications
</td>

<td align="CENTER" >Wassmuth2011
</td>

<td align="CENTER" >Journal of Veterinary Diagnostic Investigation
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >Invest-2011-Wassmuth-436-53.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Senckenberg Natural History Collections Dresden
</td>

<td align="CENTER" >Fresneda2011
</td>

<td align="CENTER" >Arthropod Systematics & Phylogeny
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >fresneda_11_phylogenetic_785869.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Senckenberg Natural History Collections Dresden
</td>

<td align="CENTER" >Mally2011
</td>

<td align="CENTER" >Arthropod Systematics & Phylogeny
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >ASP_69_1_Mally_55-71.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Senckenberg Natural History Collections Dresden
</td>

<td align="CENTER" >Shimizu2011
</td>

<td align="CENTER" >Arthropod Systematics & Phylogeny
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >ASP_69_2_Shimizu_75-81.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Springer-Verlag
</td>

<td align="CENTER" >Beermann2011
</td>

<td align="CENTER" >Zoomorphology
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >10.1007_s00435-011-0129-9.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Springer-Verlag
</td>

<td align="CENTER" >Cuezzo2011
</td>

<td align="CENTER" >Zoomorphology
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >cuezzo_11_ultrastructure_694669.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Springer-Verlag
</td>

<td align="CENTER" >Vinn2011
</td>

<td align="CENTER" >Zoomorphology
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >10.1007_s00435-011-0133-0.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Taylor & Francis
</td>

<td align="CENTER" >Bianucci2011
</td>

<td align="CENTER" >Journal of Vertebrate Paleontology
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >bianucci_11_aegyptocetus_778747.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Taylor & Francis
</td>

<td align="CENTER" >Makovicky2011
</td>

<td align="CENTER" >Journal of Vertebrate Paleontology
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >makovicky_11_new_694826.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Taylor & Francis
</td>

<td align="CENTER" >Pietri2011
</td>

<td align="CENTER" >Journal of Vertebrate Paleontology
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >pietri_11_revision_689491.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Taylor & Francis
</td>

<td align="CENTER" >Rook2011
</td>

<td align="CENTER" >Journal of Vertebrate Paleontology
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >rook_11_phylogeny_694916.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Taylor & Francis
</td>

<td align="CENTER" >Tsuihiji2011
</td>

<td align="CENTER" >Journal of Vertebrate Paleontology
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >tsuihiji_11_cranial_660620.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Taylor & Francis
</td>

<td align="CENTER" >Yates2011
</td>

<td align="CENTER" >Journal of Vertebrate Paleontology
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >yates_11_new_694821.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Taylor & Francis
</td>

<td align="CENTER" >Gerth2011
</td>

<td align="CENTER" >Systematics and Biodiversity
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >gerth_11_wolbachia_779749.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Taylor & Francis
</td>

<td align="CENTER" >Krebes2011
</td>

<td align="CENTER" >Systematics and Biodiversity
</td>

<td align="CENTER" >no
</td>

<td align="CENTER" >krebes_11_phylogeography_779700.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Sociedade Brasileira de Ictiologia
</td>

<td align="CENTER" >Britski2011
</td>

<td align="CENTER" >Neotropical Ichthyology
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >a02v9n2.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Sociedade Brasileira de Ictiologia
</td>

<td align="CENTER" >Sarmento2011
</td>

<td align="CENTER" >Neotropical Ichthyology
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >a03v9n2.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Sociedade Brasileira de Ictiologia
</td>

<td align="CENTER" >Calegari2011
</td>

<td align="CENTER" >Neotropical Ichthyology
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >a04v9n2.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Royal Society
</td>

<td align="CENTER" >Billet2011
</td>

<td align="CENTER" >Proceedings of the Royal Society B: Biological Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >billet_11_oldest_687630.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Royal Society
</td>

<td align="CENTER" >Polly2011
</td>

<td align="CENTER" >Proceedings of the Royal Society B: Biological Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >polly_11_history_625430.pdf
</td>
</tr>
<tr >

<td align="CENTER" height="19" >Royal Society
</td>

<td align="CENTER" >Sansom2011
</td>

<td align="CENTER" >Proceedings of the Royal Society B: Biological Sciences
</td>

<td align="CENTER" >yes?
</td>

<td align="CENTER" >sansom_11_decay_625429.pdf
</td>
</tr>
</tbody>
</table>
