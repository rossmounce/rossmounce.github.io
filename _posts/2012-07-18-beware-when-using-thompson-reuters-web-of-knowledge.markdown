---
author: rmounce
comments: true
date: 2012-07-18 12:53:42+00:00
layout: post
link: http://rossmounce.co.uk/2012/07/18/beware-when-using-thompson-reuters-web-of-knowledge/
slug: beware-when-using-thompson-reuters-web-of-knowledge
title: 'Beware when using Thompson Reuters Web of Knowledge '
wordpress_id: 329
categories:
- Content Mining
- Open Access
- Open Data
- Phylogenetics
- PLoS
---

just a quick post...

I'm pretty shocked at the poor indexing service given by [Thompson Reuters Web of Knowledge](http://en.wikipedia.org/wiki/ISI_Web_of_Knowledge) (or ISI Web of Science as you might know it).

I've unashamedly bashed them before and I'll bash them again here. (They deserve criticism because they're paid a lot of money to do this as a commercial for-profit enterprise, and I don't think they're doing it as well as they could be.)

I performed a very simple search today looking for the articles containing the word 'cladistic' but NOT 'phylogen*' for articles published in the year 2010. 

Topic=(cladistic) NOT Topic=(phylogen*) AND Year Published=(2010)
Refined by: Source Titles=( PLOS NEGLECTED TROPICAL DISEASES )
Databases=SCI-EXPANDED.

Below is a screenshot of just one of many of the disappointing results. I've refined the search to just the PLoS paper, to clearly show that it does come-up in this search:

[![](http://rossmounce.co.uk/wp-content/uploads/2012/07/Web-of-Science-Results.png)](http://rossmounce.co.uk/wp-content/uploads/2012/07/Web-of-Science-Results.png)


It's an Open Access paper, so we can all go see for ourselves the FULL content of the paper

Na, B.-K., Bae, Y.-A., Zo, Y.-G., Choe, Y., Kim, S.-H., Desai, P. V., Avery, M. A., Craik, C. S., Kim, T.-S., Rosenthal, P. J., and Kong, Y. 2010. [Biochemical properties of a novel cysteine protease of plasmodium vivax, vivapain-4](http://dx.doi.org/10.1371/journal.pntd.0000849). PLOS NEGLECTED TROPICAL DISEASES 4.

In which we find the text caption for figure 1 mentions 'phylogen*' twice!

[caption id="attachment_335" align="aligncenter" width="848"][![](http://rossmounce.co.uk/wp-content/uploads/2012/07/phylogen.png)](http://rossmounce.co.uk/wp-content/uploads/2012/07/phylogen.png) from Na, B.-K., Bae, Y.-A., Zo, Y.-G., Choe, Y., Kim, S.-H., Desai, P. V., Avery, M. A., Craik, C. S., Kim, T.-S., Rosenthal, P. J., and Kong, Y. 2010. Biochemical properties of a novel cysteine protease of plasmodium vivax, vivapain-4. PLOS NEGLECTED TROPICAL DISEASES 4. [http://dx.doi.org/10.1371/journal.pntd.0000849](http://dx.doi.org/10.1371/journal.pntd.0000849) CC-BY licenced[/caption]


so at the very least I suspect Web of Science (WoS) is systematically NOT indexing the caption text of figures (if you know more than I about this, please do comment). Academics rely on services like this to effectively and accurately search the literature, to perform comprehensive reviews and such. If all the textual content of science isn't actually being indexed by WoS, that's clearly going to lead to bad science at some point (e.g. a vital missing paper, not picked up in an otherwise well designed literature search). I could forgive them for not being able to OCR the text _within_ the images of figures, but NOT for the fully machine-readable text captions like this one. Furthermore, it's Open Access and fully-digital - why aren't they indexing figure caption text?


*grr* 


**UPDATE**

It appears it's not just figure caption text they don't index. Do they index only titles and abstracts?

many of the other 81 results (papers) of that search for 'cladistic' but NOT 'phylogen*' contain the word-stem 'phylogen*' in the full text of the paper!

e.g.

Wilts, E. F., Arbizu, P. M., and Ahlrichs, W. H. 2010. Description of bryceella perpusilla n. sp (monogononta: Proalidae), a new rotifer species from terrestrial mosses, with notes on the ground plan of bryceella REMANE, 1929. INTERNATIONAL REVIEW OF HYDROBIOLOGY 95. [http://dx.doi.org/10.1002/iroh.201011280](http://dx.doi.org/10.1002/iroh.201011280)

Echeverry, A. and Morrone, J. J. 2010. Parsimony analysis of endemicity as a panbiogeographical tool: an analysis of caribbean plant taxa. BIOLOGICAL JOURNAL OF THE LINNEAN SOCIETY 101. [http://dx.doi.org/10.1111/j.1095-8312.2010.01535.x](http://dx.doi.org/10.1111/j.1095-8312.2010.01535.x)

Stutz, H. L., Shiozawa, D. K., and Evans, R. P. 2010. Inferring dispersal of aquatic invertebrates from genetic variation: a comparative study of an amphipod and mayfly in great basin springs. JOURNAL OF THE NORTH AMERICAN BENTHOLOGICAL SOCIETY 29 [http://dx.doi.org/10.1899/09-157.1](http://dx.doi.org/10.1899/09-157.1)

Campo, D., Molares, J., Garcia, L., Fernandez-Rueda, P., Garcia-Gonzalez, C., and Garcia-Vazquez, E. 2010. Phylogeography of the european stalked barnacle (pollicipes pollicipes): identification of glacial refugia. MARINE BIOLOGY 157. [http://dx.doi.org/10.1007/s00227-009-1305-z](http://dx.doi.org/10.1007/s00227-009-1305-z)

Choiniere, J. N., Clark, J. M., Forster, C. A., and Xu, X. 2010. A basal coelurosaur (dinosauria: Theropoda) from the late jurassic (oxfordian) of the shishugou formation in wucaiwan, people's republic of china. JOURNAL OF VERTEBRATE PALEONTOLOGY 30. [http://dx.doi.org/10.1080/02724634.2010.520779](http://dx.doi.org/10.1080/02724634.2010.520779)

Caldwell, M. W. and Palci, A. 2010. A new species of marine ophidiomorph lizard, adriosaurus skrbinensis, from the upper cretaceous of slovenia. JOURNAL OF VERTEBRATE PALEONTOLOGY 30. [http://dx.doi.org/10.1080/02724631003762963](http://dx.doi.org/10.1080/02724631003762963)

Hastings, A. K., Bloch, J. I., Cadena, E. A., and Jaramillo, C. A. 2010. A new small short-snouted dyrosaurid (crocodylomorpha, mesoeucrocodylia) from the paleocene of northeastern colombia. JOURNAL OF VERTEBRATE PALEONTOLOGY 30. [http://dx.doi.org/10.1080/02724630903409204](http://dx.doi.org/10.1080/02724630903409204)

Karanovic, I. and McKay, K. 2010. Two new species of leicacandona karanovic (ostracoda, candoninae) from the great sandy desert, australia. JOURNAL OF NATURAL HISTORY 44. [http://dx.doi.org/10.1080/00222933.2010.502977](http://dx.doi.org/10.1080/00222933.2010.502977)

(and more, these are just some of the articles I've looked at the full-text of so far... I think it's safe to say now this is NOT a one off phenomenon)

I've now found through manual inspection that [at least 47](http://www.citeulike.org/user/rossmounce/tag/contains_phylogen) of the 'hits' for this search actually contain a 'phylogen*' word within the main text of the paper (excluding the reference list)

I guess I'm probably not the first to realise this but... wow. Is this not *really* poor service? I'm pretty sure my desktop software could do a better job of indexing than this. All it is, is simple string matching!


...and of course I _can_ do a better job of this myself with Open Access papers. All one need do is download the OA corpus from [UKPMC](http://ukpmc.ac.uk/ftp/oa) and index the *FULL* text including figure caption text and reference lists yourself. I wonder how many more relevant papers I might 'find' with my searches if I did this rather than relying on Web of Science?
