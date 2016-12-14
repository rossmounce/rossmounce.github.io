---
author: rmounce
comments: true
date: 2015-05-13 16:31:28+00:00
layout: post
link: http://rossmounce.co.uk/2015/05/13/making-a-journal-scraper/
slug: making-a-journal-scraper
title: Making a journal scraper
wordpress_id: 1790
categories:
- Content Mining
---

Yesterday, I made a journal scraper for the [International Journal of Systematic and Evolutionary Microbiology](http://ijs.sgmjournals.org/) (IJSEM).

Fortunately, [Richard Smith-Unna](https://github.com/Blahah) and the ContentMine team have done most of the hard work in creating the general framework with [quickscrape](https://github.com/ContentMine/quickscrape) (open-source and available on github), I just had to modify the available journal-scrapers to work with IJSEM.


### How did I do it?


Find an open access article in the target journal e..g [James _et al_ (2015)_ Kazachstania yasuniensis_ sp. nov., an ascomycetous yeast species found in mainland Ecuador and on the Galápagos](http://ijs.sgmjournals.org/content/65/Pt_4/1304.full)

In your browser, view the HTML source of the full text page, in the Chrome/Chromium browser the keyboard shortcut to do this is Ctrl-U. You should then see something like this, perhaps with less funky highlighting colours:

    
    <!DOCTYPE html
      PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    <html
          xmlns="http://www.w3.org/1999/xhtml"
          xml:lang="en"
          lang="en">
       <head>
          <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
          <title>Kazachstania yasuniensis sp. nov., an ascomycetous yeast species found in mainland Ecuador and on the Galápagos </title>
          <meta name="googlebot" content="NOODP" />
          <meta name="HW.ad-path" content="/cgi/content/full/65/Pt_4/1304" />
          <meta content="/ijs/65/Pt_4/1304.atom" name="HW.identifier" />
          <meta name="DC.Format" content="text/html" />
          <meta name="DC.Language" content="en" />
          <meta content="Kazachstania yasuniensis sp. nov., an ascomycetous yeast species found in mainland Ecuador and on the Galápagos"
                name="DC.Title" />
          <meta content="10.1099/ijs.0.000102" name="DC.Identifier" />
          <meta content="2015-04-01" name="DC.Date" />
          <meta content="Society for General Microbiology" name="DC.Publisher" />
          <meta content="Stephen A. James" name="DC.Contributor" />
          <meta content="Enrique Javier Carvajal Barriga" name="DC.Contributor" />
          <meta content="Patricia Portero Barahona" name="DC.Contributor" />
          <meta content="Carmen Nueno-Palop" name="DC.Contributor" />
          <meta content="Kathryn Cross" name="DC.Contributor" />
          <meta content="Christopher J. Bond" name="DC.Contributor" />
          <meta content="Ian N. Roberts" name="DC.Contributor" />
          <meta content="International Journal of Systematic and Evolutionary&#xA;                Microbiology"
                name="citation_journal_title" />


I based my IJSEM scraper on the [existing set of scraper definitions for eLife](https://github.com/ContentMine/journal-scrapers/blob/master/scrapers/elife.json) because I know both journals use similar underlying technology to create their webpages.

The first bit I clearly had to modify was the extraction of publisher. In the eLife scraper this works:

    
    {
      "url": "elifesciences\\.org",
      "elements": {
        "publisher": {
          "selector": "//meta[@name='citation_publisher']",
          "attribute": "content"
        },


but at IJSEM that information isn't specified with 'citation_publisher', instead it's tagged as 'DC.Publisher' so I modified the element to reflect that:

    
    {
      "url": "ijs\\.sgmjournals\\.org",
      "elements": {
        "publisher": {
          "selector": "//meta[@name='DC.Publisher']",
          "attribute": "content"
        },


The license and copyright information extraction is even more different between eLife and IJSEM, here's the correct scraper for the former:

    
    },
        "license": {
          "selector": "//meta[@name='DC.Rights']",
          "attribute": "text"
        },
        "copyright": {
          "selector": "//meta[@name='DC.Rights']",
          "attribute": "text"
        }


and here's how I changed it to extract that information from IJSEM pages:

    
    },
        "license": {
          "selector": "//div[contains(@class, 'license')]",
          "attribute": "text"
        },
        "copyright": {
          "selector": "//div/p[contains(@class, 'copyright')]",
          "attribute": "text"
        }


The XPath needed is completely different. The information is inside a div, not a meta tag.



Hardest of all though were the full size figures and the supplementary materials files - they're not directly linked from the full text HTML page which is rather annoying. Richard had to help me out with these by creating "followables":

In his words:

any element can 'follow' any other element in the elements array, just by adding the key-value pair `"follow": "element_name"` to the element that does the following. If you want to follow an element, but don't want the followed element to be included in the results, you add it to a `followables` array instead of the `elements` array. The followed array must capture a URL.



    
    {
       "url": "ijs\\.sgmjournals\\.org",
      "followables": {
        "figure_expansion": {
          "selector": "//div[contains(@class, 'fig-inline')]//a[text()='In this window']",
          "attribute": "href"
        },
        "suppdata_expansion": {
          "selector": "//a[@rel='supplemental-data']",
          "attribute": "href"
        }
      },
    
    ...
    
         },
         "supplementary_material": {
    -      "selector": "//a[@rel='supplemental-data']",
          "follow": "suppdata_expansion",
          "selector": "//div[@id='content-block']//a",
           "attribute": "href",
           "download": true
         },
         "figure": {
    -      "selector": "//div[contains(@class, 'fig-inline')]/a/img",
    -      "attribute": "src",
          "follow": "figure_expansion",
          "selector": "//div[contains(@class, 'fig-expansion')]/a",
          "attribute": "href",
           "download": true
         },




The bottom-line is, it might look complicated initially, but actually it's not that hard to write a fully-functioning  journal scraper definition, for use with quickscrape. I'm off to go and create one for Taylor & Francis journals now :)



Wouldn't it be nice if all scholarly journals presented their content on the web in the same way, so we didn't have to write a thousand different scrapers to download it? That'd be just too _helpful_ wouldn't it?




