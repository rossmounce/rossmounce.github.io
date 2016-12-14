---
author: rmounce
comments: true
date: 2013-10-06 19:54:50+00:00
layout: post
link: http://rossmounce.co.uk/2013/10/06/setting-up-ami2-on-windows/
slug: setting-up-ami2-on-windows
title: Setting-up AMI2 on Windows
wordpress_id: 1259
categories:
- Content Mining
---

I've been rather preoccupied in the last few months hence the lack of blog posts. (Apologies!)

Here's a quick recap of some things I've done since July:



	
  * Got married in China (in September)

	
  * Successfully proposed that the Systematics Association (of which I'm a council member) should sign [DORA](http://am.ascb.org/dora/)

	
  * Gave an invited talk on open science at an [INNGE](http://www.innge.net/) workshop at [INTECOL 2013](http://www.intecol2013.org/)

	
  * Completed and **handed-in my PhD thesis** last Thursday!


So yeah, I _really_ didn't have time blog until now.

But now my PhD thesis is handed-in I can concentrate on the next step... Matthew Wills, myself, and Peter Murray-Rust have an approved BBSRC grant to work on further developing [AMI2](http://blogs.ch.cam.ac.uk/pmr/2012/10/24/ami2-opencontentmining-an-intelligent-reader-of-the-pdf-stm-literature-we-achieve-the-first-phase-alpha-pdf2svg/) to extract phylogenetic trees from the literature (born-digital PDFs).

At the moment it is in _alpha_ stage so it doesn't extract trees perfectly - it needs work. But in case you might want to try it out I thought I'd use this post to explain how to get a test development of it running on Windows (I don't usually use Windows myself, I _much_ prefer linux). These notes are thus as much an open notebook science 'aide memoire' for myself as they are instructions for others!

**Dependencies and IDE:**

****1.) You'll need [Java JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html), [Eclipse](http://www.eclipse.org/downloads/), [Mercurial](http://mercurial.selenic.com/downloads/) and [Maven](http://maven.apache.org/) for starters.

If you haven't got this setup already you may need to set your environment variables e.g. JAVA_HOME

2.) Within Eclipse you need to install the m2e (maven integration) plugin

(from within the Eclipse GUI) click 'Help' -> Install New Software -> All available sites (from the dropdown) -> select m2e



3.) Using mercurial, clone the AMI2 suite to a clean workspace folder. The suite includes:



	
  * [euclid-dev](https://bitbucket.org/petermr/euclid-dev) (the top-level project upon which much depends)

	
  * [cmlxom](https://bitbucket.org/wwmm/cmlxom)

	
  * [svg-dev](https://bitbucket.org/petermr/svg-dev)

	
  * [html-dev](https://bitbucket.org/petermr/html-dev)

	
  * [pdf2svg-dev](https://bitbucket.org/petermr/pdf2svg-dev)

	
  * [svg2xml-dev](https://bitbucket.org/petermr/svg2xml-dev)




[euclid-dev itself has many dependencies which are indicated in its POM file which you shouldn't need to worry about - they should be pulled-in automatically. These include:  commons-io, log4j, xom, joda and junit.]

4.) From within the Eclipse GUI import your workspace of AMI2 tools:

click 'File' -> Import -> Maven -> select 'Existing Maven Projects' -> Next -> select your workspace



5.) Test if it works. In the package explorer side-pane window you should now see folders corresponding to the six AMI2 tools listed above.

Right-click on svg2xml-dev -> select 'Run-as' -> JUnit Test

and sit back and watch the test run in the console at the bottom of the Eclipse GUI.

(The tests are a little slow, have patience, it may take a few minutes - it took me 175 seconds)

To view the results, in the package explorer pane, navigate inside the svg2xml-dev document tree into /target/output/multiple-1471-2148-11-312 and click ont TEXT.0 to see what the text-extraction looks like. You should see something like this below (note it successfully gets italics, bold, and superscripts)

----------------------------------------------------------------------------------------------------




**Gene conversion and purifying selection shape** **nucleotide variation in gibbon L/M opsin genes**




Tomohide Hiwatashi 1 , Akichika Mikami 2,8 , Takafumi Katsumura 1 , Bambang Suryobroto 3 , Dyah Perwitasari-Farajallah 3,4 , Suchinda Malaivijitnond 5 , Boripat Siriaroonrat 6 , Hiroki Oota 1,9 , Shunji Goto 7,10  and Shoji Kawamura 1*






**Abstract** **Background: ** Routine trichromatic color vision is a characteristic feature of catarrhines (humans, apes and Old World monkeys). This is enabled by L and M opsin genes arrayed on the X chromosome and an autosomal S opsin gene. In non-human catarrhines, genetic variation affecting the color vision phenotype is reported to be absent or rare in both L and M opsin genes, despite the suggestion that gene conversion has homogenized the two genes. However, nucleotide variation of both introns and exons among catarrhines has only been examined in detail for the L opsin gene of humans and chimpanzees. In the present study, we examined the nucleotide variation of gibbon (Catarrhini, Hylobatidae) L and M opsin genes. Specifically, we focused on the 3.6~3.9-kb region that encompasses the centrally located exon 3 through exon 5, which encode the amino acid sites functional for the spectral tuning of the genes.

**Results: ** Among 152 individuals representing three genera ( _Hylobates_ ,  _Nomascus _ and  _Symphalangus_ ), all had both L and M opsin genes and no L/M hybrid genes. Among 94 individuals subjected to the detailed DNA sequencing, the nucleotide divergence between L and M opsin genes in the exons was significantly higher than the divergence in introns in each species. The ratio of the inter-LM divergence to the intra-L/M polymorphism was significantly lower in the introns than that in synonymous sites. When we reconstructed the phylogenetic tree using the exon sequences, the L/M gene duplication was placed in the common ancestor of catarrhines, whereas when intron sequences were used, the gene duplications appeared multiple times in different species. Using the GENECONV program, we also detected that tracts of gene conversions between L and M opsin genes occurred mostly within the intron regions.

**Conclusions: ** These results indicate the historical accumulation of gene conversions between L and M opsin genes in the introns in gibbons. Our study provides further support for the homogenizing role of gene conversion between the L and M opsin genes and for the purifying selection against such homogenization in the central exons to maintain the spectral difference between L and M opsins in non-human catarrhines.






**Background** In catarrhine primates (humans, apes and Old World monkeys) the L and M opsin genes are closely juxta-posed on the X chromosome and, in combination with the autosomal S opsin gene, enable routinely trichro-matic color vision [1,2]. The L and M opsin genes have a close evolutionary relationship and are highly similar in nucleotide sequence (~96% identity). Among 15


* Correspondence: kawamura@k.u-tokyo.ac.jp 1 Department of Integrated Biosciences, Graduate School of Frontier Sciences, The University of Tokyo, Kashiwa 277-8562, Japan Full list of author information is available at the end of the article


amino acid differences between the human L and M opsin genes, three account for the main shifts in spectral sensitivities and tuning [3-9]. The organization of the L and M opsin genes among humans is known to be variable and includes the absence of an L or M opsin gene or the presence of L/M hybrid genes with an intermediate spectral sensitivity. A high incidence (approximately 3-8%) of color vision  **“ ** deficien-cies **” ** in males results as a consequence [10].
**Hiwatashi ** _et al_ **. ** _BMC Evolutionary Biology _ **2011, ** **11** **:312** **http://www.biomedcentral.com/1471-2148/11/312**
----------------------------------------------------------------------------------------------------

If you'd like to try your own PDFs with it you'll need to do two things:

A.) place the PDF(s) to be tested within the folder:    svg2xml-dev/src/test/resources/pdfs

B.) edit the file:    svg2xml-dev/src/test/java/org/xmlcml/svg2xml/pdf/PDFAnalyzerTest.java

so that

new PDFAnalyzer().analyzePDFFile(new File(" ...

points at your file(s).



You can then right-click 'multipletest' from within PDFAnalyzerTest.java and select Run As -> JUnit Test



We're working with BMC journal content for the moment, and when we perfect it on this, we will expand our scope to include subscription access content too.




