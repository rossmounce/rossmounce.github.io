---
author: rmounce
comments: true
date: 2015-05-24 14:53:39+00:00
layout: post
link: http://rossmounce.co.uk/2015/05/24/bmnh-specimens-used-in-plos-one/
slug: bmnh-specimens-used-in-plos-one
title: BMNH specimens used in PLOS ONE
wordpress_id: 1812
categories:
- Content Mining
- Open Data
tags:
- Linked Data
---

In this post I'll go through an illustrated example of what I plan to do with my text mining project: linking-up biological specimens from the Natural History Museum, London (sometimes known as BMNH or NHMUK) to the published research literature with persistent identifiers.

I've run some simple grep searches of the PMC open access subset already, and PLOS ONE make up a significant portion of the 'hits', unsurprisingly.

Below is a visual representation of the BMNH specimen 'hits' I found in the full text of one PLOS ONE paper:

Grohé C, Morlo M, Chaimanee Y, Blondel C, Coster P, et al. (2012) New Apterodontinae (Hyaenodontida) from the Eocene Locality of Dur At-Talah (Libya): Systematic, Paleoecological and Phylogenetical Implications. **PLoS ONE** 7(11): e49054. doi: [10.1371/journal.pone.0049054](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0049054)

[![onepaper](http://rossmounce.co.uk/wp-content/uploads/2015/05/onepaper.png)](http://rossmounce.co.uk/wp-content/uploads/2015/05/onepaper.png)

I used the open source software [Gephi](http://gephi.github.io/), and the [Yifan Hu layout](http://www.mathematica-journal.com/issue/v10i1/graph_draw.html) to create the above graphical representation. The node marked in blue is the paper. Nodes marked in red are catalogue numbers I couldn't find in the [NHM Open Data Portal](http://data.nhm.ac.uk/dataset/collection-specimens) specimen collections dataset: 10 out of 34 not found.

Source data table below showing how uninformative the NHM persistent IDs are. I would have plotted them on the graph instead of the catalogue strings as that would be technically more correct (they are the _unique_ IDs), but it would look horrible.

    
    Catalogue Number   NHM Data Portal Persistent ID
    BMNH M 85319   114e7dab-b3bd-43a2-9c0f-876ec41ecfc9
    BMNH M 85318   14502273-5337-4d1b-a7dd-52375f62e684
    BMNH M 85315   273019df-4252-4640-97f4-902ba8c9fc44
    BMNH M 85321   28931039-5bcf-45ba-a531-415475515624
    BMNH M 8437    2ca4c323-5810-4b01-8dc7-cf203c973d98
    BMNH M 8436    2cdeb90c-6bb0-4430-8e2b-5873db0caca8
    BMNH M 9259    37f115c5-39cc-4d1d-994b-8a4e4fcd470f
    BMNH M 85323   38698d5e-69f3-4f5c-8bba-5543021aac44
    BMNH M 85301   477b9900-e0a7-442c-939f-048e3354bc14
    BMNH M 85313   499d8a9d-d4eb-40f8-b904-c199785cc5ff
    BMNH M 85297   49c91ade-fe6e-48a5-8fce-97c168252552
    BMNH M 8441    4b5e3722-e92a-4a8a-997e-775e1823a07e
    BMNH M 85298   4cf564e8-554d-4747-8eaa-03dd1bee0fb1
    BMNH M 85320   5877de10-5327-4fcb-9fb4-51b807e97e62
    BMNH M 9257    67033c65-667d-453c-8e69-265e640b2202
    BMNH M 85317   73dc0d26-02e4-4889-b6b3-d3617f47300e
    BMNH M 85312   87bce8d5-1b40-46a2-9f9b-15f8bd7bddae
    BMNH M 8880    a89d2901-e4c0-47cf-aef4-ce458ecb98f2
    BMNH M 8512    b1d01430-0046-4650-a111-7008f9597b35
    BMNH M 85300   cbb0d734-a052-4132-a912-7b647468d6fc
    BMNH M 85316   d789f148-3393-4a48-9143-b3bbd0ed7dee
    BMNH M 85303   ee8f78d9-84f2-425c-b2e7-7e8ca013c39f
    BMNH M 8873    f5de5e4d-bf48-45ef-8d7b-5484f9aa78fd
    BMNH M 85322   fd30af1d-9b7f-4834-8964-e1b244550c46
    BMNH M 10348	
    BMNH M 85324	
    BMNH M 85325	
    BMNH M 85326	
    BMNH M 85327	
    BMNH M 85328	
    BMNH M 85330	
    BMNH M 85331	
    BMNH M 85332	
    BMNH M 85335	
    




I've been failing to find a lot of well known entities in the online specimen collections dataset which makes me rather concerned about its completeness. High profile specimens such as _Lesothosaurus_ "BMNH RUB 17" (as mentioned [in this PLOS ONE paper, Table 1](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0007783)) can't be found online via the portal under that catalogue number. I _can_ however find [RUB 16](http://data.nhm.ac.uk/specimen/3f6e31e3-a8d1-47e6-9082-5fc0a8625d61), [RUB 52](http://data.nhm.ac.uk/specimen/0475706e-612d-4518-9c49-077c282a56ce) and [RUB 54](http://data.nhm.ac.uk/specimen/a45570d0-7a46-45e8-855f-f0bfafe121a0) but these are probably different specimens. RUB 17 is mentioned in a great many papers by many different authors so it seems unlikely that they have all independently given the specimen an incorrect catalogue number - the problem is more likely to be in the completeness of the online dataset.

Another 'missing' example is "BMNH R4947" a specimen of _Euoplocephalus tutus_ as referred to in Table 4 of this [PLOS ONE paper by Arbour and Currie](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0039323). There are two other records for that taxon, but not under R4947.

To end on a happier note, I can definitely answer one question conclusively:
What is the most 'popular' NHM specimen in PLOS ONE full text?

...it's "BMNH 37001", _Archaeopteryx lithographica_ which is referred to in full text by four different papers (see below for details).

I have feeling many more NHM specimens are hiding out in separate supplementary materials files. Mining these will be hard unless figshare gets their act together and creates a full-text API for searching their collection - I believe it's a metadata only API at the moment.

[![37001 in PLOS ONE papers](http://rossmounce.co.uk/wp-content/uploads/2015/05/2015-05-24-154548_1366x744_scrot.png)](http://rossmounce.co.uk/wp-content/uploads/2015/05/2015-05-24-154548_1366x744_scrot.png)



I've purposefully made very simple graphs so far. Once I get more data, I can start linking it up to create beautiful and complex graphs like the one below (of the taxa shared between 3000 microbial phylogenetic studies in IJSEM, unpublished), which I'm still trying to get my head around. The linked open data work continues...

[![Bacteria subutilis commonly used](http://rossmounce.co.uk/wp-content/uploads/2015/05/2015-05-22-160610_1366x744_scrot.png)](http://rossmounce.co.uk/wp-content/uploads/2015/05/2015-05-22-160610_1366x744_scrot.png)


