---
author: rmounce
comments: true
date: 2015-06-20 13:50:07+00:00
layout: post
link: http://rossmounce.co.uk/2015/06/20/deep-indexing-supplementary-data-files/
slug: deep-indexing-supplementary-data-files
title: Deep indexing supplementary data files
wordpress_id: 1830
categories:
- Conservation Hackathon
- Content Mining
- Hack days
tags:
- Conservation Hackathon
---

To prove my point about the way that supplementary data files bury useful data, making it utterly indiscoverable to most, I decided to do a little experiment (in relation to text mining for museum specimen identifiers, but also perhaps with some relevance to the [NHM Conservation Hackathon](http://conservationhackathon.org/biodiversity-hack-at-the-natural-history-museum/)):

I collected the links for [all Biology Letters supplementary data files](https://gist.github.com/rossmounce/15007089a4e42b7ab109). I then filtered out the non-textual media such as audio, video and image files, then downloaded the remaining content.

**A breakdown of file extensions encountered in this downloaded subset:**

763 .doc files
543 .pdf files
109 .docx files
75 .xls files
53 .xlsx files
25 .csv files
19 .txt files
14 .zip files
2 .rtf files
2 .nex files
1 .xml file
1 ".xltx" file

I then converted some of these unfriendly formats into simpler, more easily searchable plain text formats:

    
    for i in *.zip ; do unzip $i -d /home/ross/work/royal-soc-si/biol-letters-supp-info/transformed/unzipped_$i ; done
    for i in *.docx ; do docx2txt $i /home/ross/work/royal-soc-si/biol-letters-supp-info/transformed/$i.txt ; done
    for i in *.doc ; do catdoc -a $i > /home/ross/work/royal-soc-si/biol-letters-supp-info/transformed/$i.txt ; done
    for i in *.pdf ; do pdftotext $i > /home/ross/work/royal-soc-si/biol-letters-supp-info/transformed/$i.txt ; done
    for i in *.rtf ; do unrtf --text $i > /home/ross/work/royal-soc-si/biol-letters-supp-info/transformed/$i.txt ; done
    for i in *.xls ; do in2csv $i > /home/ross/work/royal-soc-si/biol-letters-supp-info/transformed/$i.csv ; done
    for i in *.xlsx ; do in2csv $i > /home/ross/work/royal-soc-si/biol-letters-supp-info/transformed/$i.csv ; done




Now everything is properly searchable and indexable!

In a matter of seconds I can find NHM specimen identifiers that might not otherwise be mentioned in the full text of the paper, without actually wasting any time manually reading any papers. Note, not all the 'hits' are true positives but most are, and those that aren't e.g. "NHMQEVLEGYKKKYE" are easy to distinguish as NOT valid NHM specimen identifiers:

    
    $ grep -ior 'nhm............'
    20120949_ESM_1.txt:NHMUK R6792), N
    20120949_ESM_1.txt:NHMUK R8646) in
    20120949_ESM_1.txt:NHMUK R36615, ‘
    20120949_ESM_1.txt:NHMUK R36620), 
    20120949_ESM_1.txt:NHMUK R16586). 
    20120949_ESM_1.txt:NHMUK R36620) a
    20120949_ESM_1.txt:NHMUK R16586) a
    20120949_ESM_1.txt:NHMUK R6856 was
    20120949_ESM_1.txt:NHMUK Charig ar
    20120949_ESM_1.txt:NHMUK R6856 and
    20120949_ESM_1.txt:NHMUK R6856 wer
    20120949_ESM_1.txt:NHMUK R6856 wer
    20120949_ESM_1.txt:NHMUK R6856 and
    20120949_ESM_1.txt:NHM R6856 just 
    20120949_ESM_1.txt:NHM R6856 (figu
    20120949_ESM_1.txt:NHMUK R6856 had
    20120949_ESM_1.txt:NHMUK R3592) an
    20120949_ESM_1.txt:NHMUK R6856. Th
    20120949_ESM_1.txt:NHMUK R6856). M
    20120949_ESM_1.txt:NHMUK with the 
    20120949_ESM_1.txt:NHMUK R6856 is 
    20120949_ESM_1.txt:NHMUK R6856 sug
    20120949_ESM_1.txt:NHMUK R6856. Th
    20120949_ESM_1.txt:NHMUK R6856 sug
    20120949_ESM_1.txt:NHMUK R6856, bu
    20120949_ESM_1.txt:NHMUK R6586 is 
    20120949_ESM_1.txt:NHMUK R6586 als
    20120949_ESM_1.txt:NHMUK R6586, we
    20120949_ESM_1.txt:NHMUK R6586 can
    20120949_ESM_1.txt:NHMUK R6586 was
    20120949_ESM_1.txt:NHMUK R6586 may
    20120949_ESM_1.txt:NHMUK R6856 are
    20120949_ESM_1.txt:NHMUK R6856) av
    20120949_ESM_1.txt:NHMUK R6795) in
    20120949_ESM_1.txt:NHMUK R6795 is 
    20120949_ESM_1.txt:NHMUK R6856 and
    20120949_ESM_1.txt:NHMUK R6856 and
    20120949_ESM_1.txt:NHMUK R6856 was
    20120949_ESM_1.txt:NHMUK R6856 fal
    20120949_ESM_1.txt:NHMUK R6856 is 
    20120949_ESM_1.txt:NHMUK R6856 + S
    20120949_ESM_1.txt:NHMUK R6856 whe
    20120949_ESM_1.txt:NHMUK R6856 + S
    20120949_ESM_1.txt:NHMUK 1, Tanzan
    20120949_ESM_1.txt:NHMUK R6856 and
    20120949_ESM_1.txt:NHMUK Charig ar
    20120949_ESM_1.txt:NHMUK R6856 to 
    20120949_ESM_1.txt:NHMUK) for perm
    20120949_ESM_1.txt:NHMUK) for acce
    20120949_ESM_1.txt:NHMUK Image Res
    20120949_ESM_1.txt:NHMUK, The Natu
    rsbl20060505supp.txt:NHM uncataloged
    rsbl20060505supp.txt:NHM uncataloged
    rsbl20070502supp01.doc.txt:NHM) provided v
    rsbl20090302supp3.doc.txt:NHM = The Natur
    rsbl20090302supp3.doc.txt:NHMW = Natural 
    rsbl20090302supp3.doc.txt:NHM E32070	Plan
    rsbl20090302supp3.doc.txt:NHM EE5034	Plan
    rsbl20090302supp3.doc.txt:NHM E4381	Plank
    rsbl20090302supp3.doc.txt:NHM E10384	Plan
    rsbl20090302supp3.doc.txt:NHM EE4825	Plan
    rsbl20090302supp3.doc.txt:NHM E8389	Plank
    rsbl20090302supp3.doc.txt:NHM EE8132	Plan
    rsbl20090302supp3.doc.txt:NHM EE5585	Non-
    rsbl20090302supp3.doc.txt:NHM EE ?	Non-pl
    rsbl20090302supp3.doc.txt:NHM EE1961	?	?	
    rsbl20090302supp3.doc.txt:NHM E35551	Plan
    rsbl20090302supp3.doc.txt:NHM E76539	?	Up
    rsbl20090302supp3.doc.txt:NHM EE4055	Plan
    rsbl20090302supp3.doc.txt:NHM E81494	Plan
    rsbl20090302supp3.doc.txt:NHM EE4631	?	Ap
    rsbl20090302supp3.doc.txt:NHM EE4632	?	Ap
    rsbl20090302supp3.doc.txt:NHM EE4641	Plan
    rsbl20090302supp3.doc.txt:NHM E20098	Plan
    rsbl20090302supp3.doc.txt:NHM EE4404	Plan
    rsbl20090302supp3.doc.txt:NHM EE8397	Plan
    rsbl20090302supp3.doc.txt:NHM EE2372	?	Ma
    rsbl20090302supp3.doc.txt:NHM E79718	Plan
    rsbl20090302supp3.doc.txt:NHM E40574	Plan
    rsbl20090302supp3.doc.txt:NHM EE4524	Plan
    rsbl20090302supp3.doc.txt:NHM E79415	Non-
    rsbl20090302supp3.doc.txt:NHM E45372	?	Tu
    rsbl20090302supp3.doc.txt:NHM EE2321	Plan
    rsbl20090302supp3.doc.txt:NHM EE2262	Plan
    rsbl20090302supp3.doc.txt:NHM EE4610	Plan
    rsbl20090302supp3.doc.txt:NHM E4052	Non-p
    rsbl20090302supp3.doc.txt:NHM EE191	Plank
    rsbl20090302supp3.doc.txt:NHM EE2353	Plan
    rsbl20090302supp3.doc.txt:NHM E4034	Plank
    rsbl20090302supp3.doc.txt:NHM EE2432	Plan
    rsbl20090302supp3.doc.txt:NHM E4176	Plank
    rsbl20090302supp3.doc.txt:NHM EE4048	?	Ma
    rsbl20090302supp3.doc.txt:NHM E9892	Plank
    rsbl20090302supp3.doc.txt:NHM E4979	?	Tur
    rsbl20090302supp3.doc.txt:NHM E75821	Plan
    rsbl20090302supp3.doc.txt:NHM E40974	?	Se
    rsbl20090302supp3.doc.txt:NHM E79094	Plan
    rsbl20090302supp3.doc.txt:NHM E582	Plankt
    rsbl20090302supp3.doc.txt:NHMW 2005z0083/
    rsbl20090302supp3.doc.txt:NHM E82582	?	U.
    rsbl20090302supp3.doc.txt:NHM EE7698	Plan
    rsbl20090302supp3.doc.txt:NHM E9392	Plank
    rsbl20090302supp3.doc.txt:NHM E73207	?	Al
    rsbl20090302supp3.doc.txt:NHM E43810	Plan
    rsbl20090302supp3.doc.txt:NHM 56422	?	Apt
    rsbl20090302supp3.doc.txt:NHM E83246	Plan
    20120949_ESM_5.txt:NHMUK R6856) am
    rsbl2011364supp1.doc.txt:NHM-1963.8.30.1
    rsbl2011364supp1.doc.txt:NHM-83.8.22.1; 
    rsbl2011364supp1.doc.txt:NHM-72.666; MCZ
    20120949_ESM_3.txt:NHMUK R6856). P
    20120949_ESM_3.txt:NHMUK R6856) in
    rsbl20090778supp1.doc.txt:NHM as a contro
    rsbl20090139supp1.txt:NHM, The Natura
    rsbl20090139supp1.txt:NHM R1034). As 
    rsbl20100095supp1.txt:nhm.ac.uk/resea
    20120949_ESM_2.txt:NHMUK R6856) in
    20120949_ESM_2.txt:NHMUK R6856) in
    rsbl20130051supp4.txt:NHMQEVLEGYKKKYE
    rsbl20130051supp3.txt:NHMDLEDLRKKYETE
    rsbl20080409supp01.doc.txt:NHMW1997z/0000 
    rsbl20080409supp01.doc.txt:NHMW, Naturhist
    rsbl20130021supp1.doc.txt:NHM, Staatliche
    rsbl20130021supp1.doc.txt:NHMUK PV R498 a
    rsbl20130021supp1.doc.txt:NHMUK PV OR3612
    rsbl20130021supp1.doc.txt:NHMUK PV R3938 
    rsbl20130021supp1.doc.txt:NHMUK PV R5465)
    rsbl20130021supp1.doc.txt:NHMUK PV OR2003
    rsbl20130021supp1.doc.txt:NHMUK PV R1158)
    rsbl20130021supp1.doc.txt:NHMUK PV R5595)
    rsbl20130021supp1.doc.txt:NHMUK PV R4086)
    rsbl20130021supp1.doc.txt:NHMUK and GLAHM
    rsbl20130021supp1.doc.txt:NHM); Sveltonec
    rsbl20130021supp1.doc.txt:NHMUK PV R11185
    rsbl20130021supp1.doc.txt:NHM1284-R); Mal
    rsbl20130021supp1.doc.txt:NHMUK PV R6682)
    rsbl20130021supp1.doc.txt:NHMUK PV R6682)
    rsbl20130021supp1.doc.txt:NHMUK in 1959, 
    rsbl20130021supp1.doc.txt:NHMUK. While th
    rsbl20130021supp1.doc.txt:NHMUK PV R6682 
    rsbl20130021supp1.doc.txt:NHMUK PV R6682)
    rsbl20130021supp1.doc.txt:NHMUK PV R6682,
    rsbl20130021supp1.doc.txt:NHMUK PV R6682,
    rsbl20130021supp1.doc.txt:NHMUK PV R6682 
    rsbl20130021supp1.doc.txt:NHMUK) for the 
    20120949_ESM_4.txt:NHMUK R6856) wh




Perhaps this approach might be useful to the PREDICTS / LPI teams, looking for species occurrence data sets?

I don't know why [figshare](http://figshare.com/) doesn't do deep indexing by default - it'd be really useful to search the morass of published supplementary data that out there!
