---
author: rmounce
comments: true
date: 2015-01-05 19:30:54+00:00
layout: post
link: http://rossmounce.co.uk/2015/01/05/dark-research-behind-the-preprint/
slug: dark-research-behind-the-preprint
title: 'Dark Research: behind the preprint'
wordpress_id: 1561
categories:
- Phylogenetics
- PLoS
- Publications
---

This post is about my new preprint I've uploaded to PeerJ PrePrints:

[**Mounce, R. (2015) Dark Research: information content in some paywalled research papers is not easily discoverable online. PeerJ PrePrints**](https://peerj.com/preprints/773v1/)

Needless to say, it's not peer-reviewed yet but you can change that by commenting on it at the excellent [PeerJ PrePrints website](https://peerj.com/preprints/). All feedback is welcome.

The central hypothesis of this work is that content in some academic journals is less discoverable than in other journals. What do I mean discoverable? It's simple really. Imagine a paper is a bag-of-words:

cat
sat
mat
**rat**
fat
hat

If academic search providers like Google Scholar, Web of Knowledge, and Scopus can correctly tell me that this paper contains the word 'rat' then this is good and what science needs. If they can't find it, it's bad for the funders, authors and potential readers of that paper - the rat research remains hidden as 'dark research', published but not easily found. More formally, in terms of information retrieval you can measure search performance across many documents by assessing [**recall**](http://en.wikipedia.org/wiki/Information_retrieval#Recall).

Recall is defined as:

the fraction of the documents that are relevant to the query that are successfully retrieved

As a toy example: if there are 100 papers containing the word 'rat' in Zootaxa, and Google Scholar returns 50 search results containing the word 'rat' in Zootaxa, then we ascertain that Google Scholar has 50% recall for the word 'rat' in Zootaxa.

In my preprint I test recall for terms related to my subject-area against >20,000 full text papers from PLOS ONE & Zootaxa. The results are really intriguing:



	
  * Web of Knowledge is shown to be consistently poor at recall across both journals (not surprising, it only indexes titles, abstracts and keywords - woeful at detecting words that are typically present only in the methods section).

	
  * Google Scholar appears to have near-perfect recall of PLOS ONE content (open access), but less than 50% recall on average of Zootaxa content.

	
  * Scopus shows an inverse trend: reasonably consistent and good recall of Zootaxa content, averaging ~70% recall for all tests but poorer at recalling PLOS ONE content (45% recall on average).




Why is Google Scholar so poor at recalling terms used in Zootaxa papers? Is it because Zootaxa is predominantly a subscription access journal?



Why is Scopus so poor at recalling terms used in PLOS ONE papers? PLOS ONE is an open access journal, published predominantly under CC-BY - there should be no difficulty indexing it. Google Scholar demonstrates that it can be done well.



Why is Scopus so much better than Google Scholar at indexing terms in Zootaxa? What does Scopus do, or have that Google Scholar doesn't?



I don't pretend to have answers to these questions - academic search providers tend to be incredibly opaque about how they operate. But it's fascinating, and slightly worrying for our ability to do research effectively if we can't know where knowledge has been published.

**More general thoughts**

Why is academic content search so bad in 2015? It's really not that hard for born-digital papers! Is this another sign that academic publishing is broken? Discoverability is broken & inconsistent. Access is broken & inconsistent. Peer review is broken & inconsistent. Hiring & tenure is broken & inconsistent...



The good news is; there's a clear model for success here if we can identify its exact determinants: PLOS ONE & Google Scholar provide excellent discoverability (>95%). Whatever they're doing, I suggest publishers [copy it](http://neurodojo.blogspot.co.uk/2013/09/zune-journals.html) to ensure high discoverability of research.




