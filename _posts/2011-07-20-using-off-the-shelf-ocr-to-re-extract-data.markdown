---
author: rmounce
comments: true
date: 2011-07-20 14:06:09+00:00
layout: post
link: http://rossmounce.co.uk/2011/07/20/using-off-the-shelf-ocr-to-re-extract-data/
slug: using-off-the-shelf-ocr-to-re-extract-data
title: Using off-the-shelf OCR to re-extract data
wordpress_id: 121
categories:
- Content Mining
- Palaeontology
- Phylogenetics
---

Having just written a lengthy blog post / rant about publishing data for another blog (I’ll link to it later if/when it gets published). I thought I’d post a technical demonstration of my issues here.

I want need to extract simple matrices of numbers from research papers for my PhD research. Theoretically, I shouldn’t even need to do this. In an ideal world where funding/author/researcher effort (overall) was time and cost efficient, all the data I need would be automatically (and indeed _mandatorily_ submitted) to proper phylogenetic data repositories like [TreeBASE](http://treebase.org/) or [MorphoBank](http://morphobank.org/) but it isn’t. It’s just lazily and inappropriately lobbed into pdfs with little thought or care as to it’s potential re-use legacy or fidelity…

So I have to do embarrassingly complicated and time-consuming things to re-extract this simple data AND then put it in a usable form (reformatting). Scarily enough, a lot of the time, I have to resort to OCR scanning to re-extract data. Below is such a case, rather ironically from a freely-accessible (Open Access? it’s unclear) paper; sure it’s openly _accessible_ but it’s certainly NOT openly re-usable data-wise!

Orozco, J. & Philips, T. K. [Phylogenetic analysis of the american genus euphoria and related groups based on morphological characters of adults (coleoptera: Scarabaeidae: Cetoniinae: Cetoniini)](http://dx.doi.org/10.1163/187631210X12628483805310). _Insect Systematics Evolution_ 39-54 (2010)

The data I need is in a table printed sideways AND unnecessarily split between two separate pages: a classic example of deranged/lazy print-based thinking in an otherwise _digital_ world. _[Update: if it's not clear already, my ire is for publishers only. I absolve all authors of any 'blame' particularly in the case I present here, just FYI ]_

[![sidebyside](http://farm7.static.flickr.com/6127/5957563730_9f9357c881_b.jpg)](http://www.flickr.com/photos/63732388@N07/5957563730/)

Using this (below) image as my test object, I thought I’d test out a variety of free OCR options at my disposal – I’m aware these options are very basic. _If you know of anything better, or have tips on how I can ‘train’ tesseract to perform better then please fire away – I’m all ears _

1.) Google Docs OCR

2.) http://www.free-ocr.com/

3.) http://www.onlineocr.net/

4.) http://www.newocr.com/

5.) [tesseract](http://code.google.com/p/tesseract-ocr/)

**Method (in brief):** page 45 pdf -> png image -> rotate to correct orientation -> OCR

[![7C8v](http://farm7.static.flickr.com/6140/5957030013_87475b9cf3.jpg)](http://www.flickr.com/photos/63732388@N07/5957030013/)

**Results (verbatim):**

1.) **_Google – where did the taxon names go!!!!_**

1201100000 210110000? 04?0100400 2010000001 2101100010 2101000000 2100011001 2101000000 2101000001 2100010210 010 1 100000 1 20 1 000000 200 0020000 2000020000 200 003 0000 101 1020000 1010020000 0001101000 2200021000 0101101000

00000 120 00 on 000020 10 0000020000 0000000000 0000000000 l 0000 020 1 0 DU 000 020 1 U DU O00 O20 1 U DD 000 020 00 O0 0000 10?!) 0000010010 0101000010 0100010010 1000010010 0100010010 1101000010 1100000010 0100010010 0000010010 0i‘000lI|010

0011011000 0011010001 110103011? 2000010000 2000030000 0012131001 0010031001 00—0030000 0000130000 0010130001 0002111000 00l—031000 0011031000 0011031000 0011031000 0012031000 0012031001 00-0010000 0011031000 00—00I0000′

0000000011 000010011

00-01000!)0000100001 1000100001 1000011011 1000001111 0000001111 0111001011 110?!) U1-1 0000001011 001101111

0000001011 0000001011 0000001111 0000001011 0000011011 01?00010l1 0000011111 0010001011

0001000 0000??0 10100-0 0l00??0 00200-0 101

0021000 0101000 0021000 202 1010 2021000 2021000 2021000 2021000 2021000 2021000‘ 0021000 2022000 1021000

2.) **_free-ocr: wouldn’t work with .png so I converted to .jpg_**

Diplognat/ya gagates 1201100000 0000012000 0011011000 0000000011 2000000011 0001000

Coptomia aliveri 210110000? 0000002010 0011010001 000010011 0000200010 0000??0

P/medirmu meridionalis 04?0100400 0000020000 110103011? 00-010000— 0010000011 10100-0

Poerilopharis so/:0:/2i 2010000001 0000000000 2000010000 0000100001 0000000001 0100??0

Tmesorrbina uiridirinrta 2101100010 0000000000 2000030000 1000100001 0000200100 00200-0

Oxycetoniajucunda 2101000000 1000002010 0012131001 1000011011 2000201011 1011??0

Oxyt/ryrmﬁnmta 2100011001 0000002010 0010031001 1000001111 100021101? ?0210-0

Cetonia aumta 2101000000 0000002010 00—0030000 0000001111 ?100001000 0021000

R/nzbdoti: sobrina 2101000001 0000002000 0000130000 0111001011 ?000210011 0101000

E/aphinis irrorata 2100010210 00000010?0 0010130001 110?0 01-1 000021001? 0021000

E auita 0101100000 0000010010 0002111000 0000001011 0000001000 2021010

E. basalis 1201000000 0101000010 001-031000 001101111 0001001011 2021000

E. biguttata 2000020000 0100010010 0011031000 0000001011 2000011011 2021000

E. lineoligem 2000020000 1000010010 0011031000 0000001011 2000011011 2021000

E. mnescms 2000030000 0100010010 0011031000 0000001111 0000011011 2021000

E subtammtasa 1011020000 1101000010 0012031000 0000001011 2000111011 2021000

E. histronim 1010020000 1100000010 0012031001 0000011011 3000011011 2021000

E. fasnfem 0001101000 0100010010 00—0010000 01?000l011 100000-011 0021000

E. pulcbelbz 2200021000 0000010010 0011031000 0000011111 0000012011 2022000

E. mndezei 0101101000 0?00000010 00—0010000 0010001011 1000001000 1021000

3.) **_onlineocr.net doesn’t seem to like numbers greater than 1_**

0001001 0001000001 1101000100 0000100-00 0100000010 0001011010 ’2.7.4, Y 0000000 1100100000 1111100000 000101100 0100100000 00010000ZZ 47/.P7.d’i 0001000 110-000001 1101000110 0000100-00 0100100010 0001011000 m=f,,,,,f ’1 0001000 1101100000 1101100000 100100100 0100000011 0000000101 4,00.o01 0001000 1101110000 1101000000 000100100 0100001011 0000001101 r5omazuwq,15 y 000100? 1101100000 1111000000 0001001100 0100100010 000000000 5,..,52m4′,Y 0001000 1101100000 1101000000 0001001100 0100100001 0000000000 ,,,,,,p2m,/ Y 0001000 1101100000 1101000000 0001001100 0100100010 0000000000 orm.19 ’1 0001000 1101001000 111101100 000100-100 0100001010 0000001001 5701 ’1 0101000 0001000000 1101000000 0001110000 0100100000 0000011010 ’1.4′Y 0001000 /100100000 1-100/011 1000010100 0101000000 0100100010 0001010 1100100001 1101001110 0000010000 0000000000 100000101? 0001000 0001000011 1111000000 0000000-00 0100000000 0000001011 0-01002 /101100001 1111000001 100100100 0100000000 1001100011 001101 1101000000 1101100001 1001010100 0100000001 0000001011 70,..,,,,,I.6,0 0-00Z00 0010000000 1000010001 000000000? 0000000000 0100011010 4,..,.’0′.,,,1″°52.1 000010 1000000000 1000010000 0000100000 0000000000 1000000100 ’0′”0″‘”7′?’ ‘V 0-00101 1100000100 -00■01010 i11001011 0000000000 004001010 0110000 0100000000 I 1001011110 1000101100 0100000000 1000011010 iddaqormuodop 0001010 1100000000 1100000000 0001101100 0000100000 0000011001 ,darvraoldi,

4.) **_newocr provides annoyingly columnar output_**

lD§pbgnanbagwgunn

Cﬁpmnﬁanﬁuni

Phanhhuninrruﬁnnaﬂk

lhnihyimrksdwrhi

Tmrmrr/Jina viridirinrta

Chgnﬂvniajurunah

Cbgwkwwaj%nznu

Cnnnia aumta

R/Jabdntis mbrina

ELI];/Jinis irmrata

Eiawhw

Eihwaﬁs

Eibgwnum

E. /inm/igmz

Eirannrnu

lisubnvnrnnwa

Eihknwnhw

Eifkrﬁkw

Eipuhhrﬂa

Eiranakzn

1201100000

210110000?

04?0100400

2010000001

2101100010

2101000000

2100011001

2101000000

2101000001

2100010210

0101100000

1201000000

2000020000

2000020000

2000030000

1011020000

1010020000

0001101000

2200021000

0101101000

0000012000

0000002010

0000020000

0000000000

0000000000

1000002010

0000002010

0000002010

0000002000

00000010?0

0000010010

0101000010

0100010010

1000010010

0100010010

1101000010

1100000010

0100010010

0000010010

0?00000010

0011011000

0011010001

110103011?

2000010000

2000030000

0012131001

0010031001

00-0030000

0000130000

0010130001

0002111000

001-031000

0011031000

0011031000

0011031000

0012031000

0012031001

00-0010000

0011031000

00-0010000

0000000011

000010011

00-010000-

0000100001

1000100001

1000011011

1000001111

0000001111

0111001011

110?001-1

0000001011

001101111

0000001011

0000001011

0000001111

0000001011

0000011011

01?0001011

0000011111

0010001011

2000000011

0000200010

0010000011

0000000001

0000200100

2000201011

100021101?

?100001000

?000210011

000021001?

0000001000

0001001011

2000011011

2000011011

0000011011

2000111011

3000011011

100000-011

0000012011

1000001000

0001000

0000H0

10100-0

0100H0

00200-0

1011H0

?0210-0

0021000

0101000

0021000

2021010

2021000

2021000

2021000

2021000

2021000

2021000

0021000

2022000

1021000

5.) **_tesseract: only takes .tif flattened and decompressed_**

Dq>/agmztbugagutn 1201 100000 0000012000 001101 1000 0000000011 200000001 1 0001000

Captnmm a/mn: 2101 10000? 0000002010 0011010001 00001001 1 0000200010 0000??0

Pbardnmn mrnduzmz/u 04?0100400 0000020000 1 1010301 1? 0040100004 001000001 1 1010040

Parr:/apburxx xrbarbx 2010000001 0000000000 2000010000 0000100001 0000000001 0100??0

Tmrmnbzmz zuudmmta 2101 100010 0000000000 2000030000 1000100001 0000200100 0020040

Oxyrrtnnxapnxné 2101000000 1000002010 0012131001 1000011011 2000201011 1011??0

Oxytbyrrujiannta 210001 1001 0000002010 0010031001 1000001 1 11 100021 101? ?021040

Crtama mmzta 2101000000 0000002010 0040030000 0000001 1 11 ?100001000 0021000

Rhalzdatu mbnmz 2101000001 0000002000 0000130000 011 1001011 ?000210011 0101000

Ehphmn ummm 2100010210 0000001020 0010130001 110?0 0141 000021001? 0021000

E, mum 0101100000 0000010010 0002111000 0000001011 0000001000 2021010

E, [mm/:1 1201000000 0101000010 0014031000 001101111 0001001011 2021000

E, Ingmtuta 2000020000 0100010010 0011031000 0000001011 2000011011 2021000

E, /mm/zgmz 2000020000 1000010010 0011031000 0000001011 200001 101 1 2021000

E nmnrrm 2000030000 0100010010 0011031000 0000001 1 11 000001 101 1 2021000

E, mlztamrmam 1011020000 1101000010 0012031000 0000001011 2000111011 2021000

E, butmmnz 1010020000 1100000010 0012031001 0000011011 3000011011 2021000

E,jb.rry}m 0001 101000 0100010010 0040010000 01?000101 1 100000401 1 0021000

E, pu/[hr/M 2200021000 0000010010 0011031000 0000011111 0000012011 2022000

E mndrzr: 0101 101000 0?00000010 0040010000 0010001011 1000001000 1021000

**Discussion:**

Even though the image is reasonably high-res, not one of the tools managed 100% accuracy.

Only_ tesseract _and _free-ocr_ show any promise of being a viable solution. At the moment _free-ocr_ seems demonstrably better at the names than _tesseract_ but this could change if I start [training](http://code.google.com/p/tesseract-ocr/wiki/TrainingTesseract3) tesseract in italicised Latin binomials.

Finally, to make it a usable [nexus file](http://en.wikipedia.org/wiki/Nexus_file) I have to add the metadata wrappers above and below with extra parameters added in, discovered only by manually reading through the paper; so it eventually looks like this:

#NEXUS

[THIS IS AN OPTIONAL COMMENT:

Orozco, J. & Philips, T. K. Phylogenetic analysis of the american genus euphoria and related groups based on morphological characters of adults (coleoptera: Scarabaeidae: Cetoniinae: Cetoniini). Insect Systematics & Evolution 39-54 (2010). URL http://dx.doi.org/10.1163/187631210X12628483805310.]

BEGIN DATA;

DIMENSIONS NTAX =20 NCHAR=57;

FORMAT DATATYPE = STANDARD GAP =- MISSING =? SYMBOLS = “0 1 2 3 4″;

MATRIX

Diplognatha_gagates 1201100000 0000012000 0011011000 0000000011 2000000011 0001000

Coptomia_oliveri 210110000? 0000002010 0011010001 000010011 0000200010 0000??0

Phaedimus_meridionalis 04?0100400 0000020000 110103011? 00-010000- 0010000011 10100-0

Poecilopharis_schochi 2010000001 0000000000 2000010000 0000100001 0000000001 0100??0

Tmesorrhina_viridicincta 2101100010 0000000000 2000030000 1000100001 0000200100 00200-0

Oxycetonia_jucunda 2101000000 1000002010 0012131001 1000011011 2000201011 1011??0

Oxythyrea_funesta 2100011001 0000002010 0010031001 1000001111 100021101? ?0210-0

Cetonia_aurata 2101000000 0000002010 00-0030000 0000001111 ?100001000 0021000

Rhabdotis_sobrina 2101000001 0000002000 0000130000 0111001011 ?000210011 0101000

Elaphinis_irrorata 2100010210 00000010?0 0010130001 110?0 01-1 000021001? 0021000

E.avita 0101100000 0000010010 0002111000 0000001011 0000001000 2021010

E.basalis 1201000000 0101000010 001-031000 001101111 0001001011 2021000

E.biguttata 2000020000 0100010010 0011031000 0000001011 2000011011 2021000

E.lineoligera 2000020000 1000010010 0011031000 0000001011 2000011011 2021000

E.canescens 2000030000 0100010010 0011031000 0000001111 0000011011 2021000

E.subtomentosa 1011020000 1101000010 0012031000 0000001011 2000111011 2021000

E.histronica 1010020000 1100000010 0012031001 0000011011 3000011011 2021000

E.fascifera 0001101000 0100010010 00-0010000 01?000l011 100000-011 0021000

E.pulchella 2200021000 0000010010 0011031000 0000011111 0000012011 2022000

E.candezei 0101101000 0?00000010 00-0010000 0010001011 1000001000 1021000

;

end;

**Final step:** checking (validation) the file works by reading it into a suitable nexus file reading program e.g. [PAUP](http://paup.csit.fsu.edu/)

After all that effort – I discover that there’s a huge problem with the published dataset:

taxon 2: _Coptomia oliveri_ only has 56 characters coded in the printed matrix.

It’s not all that obvious immediately – partly _because_ the matrix is printed sideways and split over two pages; I feel this has rather aided and abetted this mistake to escape the corrective gaze of peer review. Indeed I’m led to believe that it’s rather common for underlying data to go entirely uncritiqued and unobserved during the review process. Rather odd considering data is the very basis for most phylogeny scientific papers!

This makes the entire dataset unusable for my purposes and I’ll now have to run the gauntlet of finding a current email address for the author, composing and sending an email, and then waiting indefinitely for a possible response in which they may or may not send me the correct data.

This is sadly not an uncommon situation, and I have tried to make my fellow colleagues aware of this. Only just recently I gave a talk [here](http://prezi.com/rwyvfb9bvec_/nullius-in-calculo/) at the Systematics Association biennial meeting, on the very subject of data publishing. I doubt it’ll have made much impact, but I’m happy with myself for at least raising the issue in a public forum.

When will the madness of burying, corrupting, obfuscating and generally throwing-away valuable data end? Data is far more useful in it’s original, usable formats, and in most cases I’d argue it’s easier/better for all stakeholders (funders, authors, publishers, re-users, readers…) if it’s left this way.

But in the meantime, I’ll just have to keep digging away at those pdfs to extract the data I need…

***sighs***

Comments resurrected from the old blog:

Graeme Lloyd
This story is in no way familiar...

Personally I have NEVER trusted OCR to do the job right and so have typed in countless numbers of these by hand.

A Liked Reply
10 months ago 2 Likes

Ross Mounce
I should probably make clear as well (thanks for the prompt) that I too *never* trust OCR, I always carefully check line-by-line what it gives me - but I do use it for large and/or awkward matrices.

Edit Reply
10 months ago in reply to Graeme Lloyd

alf
Why OCR? It's not an image PDF; easy enough to copy/paste the data out of the table: https://spreadsheets.google.co...

(not quite as easy as it could have been, but not too difficult)

Like Reply
10 months ago

Ross Mounce
You've copied out Table 1 which is on page 42, yes; I can do this easily too.

I want the Table 2 that's split between pages 44 and 45. Get that with perfect fidelity (e.g. formating preserved) and not much fuss and then and only then will I be impressed ;)

:P

Edit Reply
10 months ago in reply to alf

Alf Eaton
Table 2 is in that spreadsheet as well, in a separate tab. It took a quick regexp and a couple of manual edits to restore the tabulation, that's all.

Like Reply
10 months ago in reply to Ross Mounce

Ross Mounce
okay, pdftotext command-line hackery can harvest the data with fidelity. But the tabulation (formatting) is still screwed, and like you said requires manual effort to put back in place

Edit Reply
10 months ago in reply to Alf Eaton

Alf Eaton
I just copy/pasted the table from Adobe Reader - no need for command-line tools. That was my point, really: unless the PDF is a scanned image, the data's right there to be copied... It's not as nice as if it was HTML, obviously, but much easier than trying to OCR something that isn't even an image :-)

Like Reply
10 months ago in reply to Ross Mounce

bljog
Sorry, can't remember the specifics of GOCR but tesseract-OCR performed better in later benchmarking for phylogeny labels.

Like Reply
10 months ago

Ross Mounce
Seems like I'm certainly not the only one that needs to do this kind of stuff. Joseph Hughes had a go a few years ago (and seems to have had some excellent results using GOCR):
http://evo-karma.blogspot.com/...

Slightly different data, but same problem, and same methods :)

Edit Reply
10 months ago

Ross Mounce
Just tried GOCR. I converted the image into a .pcx file with GIMP and then ran: 'gocr .pcx' and got a load of gibberish back...

_n_n_n_nn_n_n_nn_________%%_,mM,:__5____,,__,v_,_,_v_, _____,_,_?_?____ _,_,_m_ _v___._, n,

methinks I'm probably doing something wrong...

Edit Reply
10 months ago in reply to Ross Mounce
