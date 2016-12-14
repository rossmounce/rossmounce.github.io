---
author: rmounce
comments: true
date: 2015-03-19 22:09:45+00:00
layout: post
link: http://rossmounce.co.uk/2015/03/19/how-to-block-readcube-and-why/
slug: how-to-block-readcube-and-why
title: How to Block Readcube and Why
wordpress_id: 1699
categories:
- Generation Open
- Hack days
- Open Science
---

Wiley & Readcube have done something rather sneaky recently, and it's not escaped the attention of diligent readers of the scientific literature.


<blockquote>Dear [@wileyonlinelib](https://twitter.com/wileyonlinelib), If I ask for a PDF, don't shove [@readcube](https://twitter.com/readcube) HTML at me, give me the PDF! If I wanted HTML, I'd have asked for it!

— Gavin Simpson (@ucfagls) [March 2, 2015](https://twitter.com/ucfagls/status/572458659411828736)</blockquote>






<blockquote>
This [@readcube](https://twitter.com/readcube) default download choice in [@BiolSciNews](https://twitter.com/BiolSciNews) is truly annoying. I only want the PDF, not to be asked to create another account.

— CarnivoreScience (@CarnivoreSci) [March 11, 2015](https://twitter.com/CarnivoreSci/status/575670541580955648)
</blockquote>





[![excellent facebook comment](http://rossmounce.co.uk/wp-content/uploads/2015/03/rename.png)](http://rossmounce.co.uk/wp-content/uploads/2015/03/rename.png)


<blockquote>Wiley now flat out hide PDF link and make you read a ReadCube mockup ("…/epdf") with link to download PDF not viewable in browser ¬_¬

— Louis (@biochemistries) [March 15, 2015](https://twitter.com/biochemistries/status/576924917247188992)</blockquote>




On the article landing page for some, if not all(?) journal articles at Wiley, in JavaScript enabled web browsers they've replaced all links to download the PDF file of the article with links that direct you to Readcube instead.

This is incredibly annoying - **they are literally forcing us to use Readcube**. That is not cool.

Some will rush to the defence of Readcube and point out that if they detect you have the rights to, you can download the PDF from within Readcube, but that's missing the point. No-one need waste their precious time whilst Readcube takes ages to load in your browser tab, when all you wanted in the first place was the PDF.

What Readcube provides IS NOT EVEN PDF. It's a mishmash of JavaScript, HTML and [DRM technology](http://en.wikipedia.org/wiki/Digital_rights_management). Thus when Wiley has icons saying "get PDF" they're lying. Clicking the "get PDF" link does NOT send you to the PDF. It sends you to Readcube's proprietary, rights-restricted mock-up of a PDF.

It doesn't even render the figure images properly, sometimes missing important bits e.g. this figure (below):
[![cubeFAIL](http://rossmounce.co.uk/wp-content/uploads/2015/03/cubefuckup.jpg)](http://rossmounce.co.uk/wp-content/uploads/2015/03/cubefuckup.jpg)

Luckily there's a simple solution: you can block Readcube in your browser settings and get simple, _direct_ one-click access to PDF files again by selectively disabling JavaScript on all Readcube-infected websites e.g. [onlinelibrary.wiley.com](http://www.onlinelibrary.wiley.com), [nature.com](http://www.nature.com) and [link.springer.com](http://link.springer.com)

**Firefox users**

Install the add-on called [YesScript](https://addons.mozilla.org/en-us/firefox/addon/yesscript/) and 'blacklist' all Readcube-tainted websites.

**Google Chrome / Chromium users**

Use Vince Buffalo's '[Get Me the F**king PDF](https://github.com/vsbuffalo/gmtfPDF)' Chrome plugin. It's really good.
<strike>This browser is so clever you don't even need to install anything new. Selective JavaScript blacklisting of websites is an in-built function:

A) Click the menu button in the top right hand corner of your browser
B) Select Settings
C) (scroll to bottom) Click Show advanced settings
D) Underneath the "Privacy" section, click the "Content settings" button.
E) Under the "Javascript" section, click "Manage Exceptions" and add at least these three Readcube-infected websites: [onlinelibrary.wiley.com](http://www.onlinelibrary.wiley.com), [nature.com](http://www.nature.com) and [link.springer.com](http://link.springer.com) (example screenshot below)</strike>

[![javascript-chrome](http://rossmounce.co.uk/wp-content/uploads/2015/03/javascriptchrome.png)](http://rossmounce.co.uk/wp-content/uploads/2015/03/javascriptchrome.png)

**Safari users**

I haven't tested this but the [JavaScript Blocker](http://javascript-blocker.toggleable.com) extension looks like it should do the job.

**Internet Explorer users**

I'm tempted to say: install Chrome or Firefox but I'm well aware that some unfortunate academics have 'university-managed' computers on which they can't easily install things. If so try the instructions for [IE here](http://www.technipages.com/internet-explorer-enabledisable-javascript). Let me know if you have better solutions for unfortunate IE users.

[caption id="attachment_1724" align="alignnone" width="444"][![Before (left) and After (right) disabling JavaScript on the page.](http://rossmounce.co.uk/wp-content/uploads/2015/03/cubed.png)](http://rossmounce.co.uk/wp-content/uploads/2015/03/cubed.png) Before (left) and After (right) disabling JavaScript on the page.[/caption]

**Added bonus function - extra privacy!**

Would you want advertisers to be collecting data on you, knowing what you've been reading? It's possible, though not proven AFAIK that the journal publishers themselves, or the advertisers they use are recording information about what articles you're reading. They might know you read that article about [average penis length](http://onlinelibrary.wiley.com/doi/10.1111/bju.13010/abstract) three times last week for instance... Eric Hellman wrote quite an [alarming post about the extent of this tracking at publisher websites](http://go-to-hellman.blogspot.co.uk/2015/03/16-of-top-20-research-journals-let-ad.html) recently. Thus blocking JavaScript at publisher websites provides extra privacy, not just protection against Readcube!

Above all I think we should [#BlockReadcube](https://twitter.com/search?q=%23BlockReadcube) not just for our own utility (easier access to the real PDF), but to send them a powerful message: we do not want the literature to be assimilated and enclosed in rights-restrictions by new technology. We do not want non-consenting 'cubification of the research literature. We are Starfleet, and as far as I'm concerned: **Readcube is the [Borg](http://en.wikipedia.org/wiki/Borg_%28Star_Trek%29)**.

[![assimilate-readcube](http://rossmounce.co.uk/wp-content/uploads/2015/03/assimilate-readcube.png)](http://rossmounce.co.uk/wp-content/uploads/2015/03/assimilate-readcube.png)

PS If you like some of the features of Readcube, try [Utopia Docs](http://utopiadocs.com/) - it's free and it's released under an Open Source license, and it doesn't force you to use it!

_Update 2015-03-20: This post does not indicate I'm suddenly 'in favour' of PDF's by the way, as some seem to have interpreted. If Wiley wanted to do something good, they should publish their full text XML on site like other good publishers do e.g. PLOS, eLife, Hindawi, MDPI, Pensoft, BMC, Copernicus... If they did this then readers could choose to use innovative open source viewing software such the [eLife Lens](https://github.com/elifesciences/lens/). That kind of change would add value & choice, rather than subtract value (& rights) as they have in this case._

**Further discussion of Readcube and rights-restrictions:**

[http://biochemistri.es/post/104293317361/nature-and-its-extended-family-of-journals-were](http://biochemistri.es/post/104293317361/nature-and-its-extended-family-of-journals-were)

[http://rossmounce.co.uk/2014/12/02/beggar-access/](http://rossmounce.co.uk/2014/12/02/beggar-access/)
