---
author: rmounce
comments: true
date: 2015-09-30 21:43:42+00:00
layout: post
link: http://rossmounce.co.uk/2015/09/30/using-the-nhm-data-portal-api/
slug: using-the-nhm-data-portal-api
title: Using the NHM Data Portal API
wordpress_id: 1933
categories:
- Content Mining
- NHM
---

Anyone care to remember how awful and unusable the web interface for accessing the NHM's specimen records used to be? Behold the horror below as it was in 2013, or visit the [Web Archive](http://web.archive.org/web/20130702200732/http://www.nhm.ac.uk/research-curation/scientific-resources/collections/zoological-collections/zoology-specimen-database/index.php) to see just how bad it was. It's not even the 'look' of it that was the major problem - it was more that it simply wouldn't return results for many searches. No one I know actually used that web interface because of these issues. And obviously there was no [API](https://en.wikipedia.org/wiki/Application_programming_interface).

[caption id="attachment_1937" align="aligncenter" width="960"][![2013. It was worse than it looks.](http://rossmounce.co.uk/wp-content/uploads/2015/09/oldcrap.png)](http://rossmounce.co.uk/wp-content/uploads/2015/09/oldcrap.png) 2013. It was _worse_ than it looks.[/caption]

The internal database that the NHM uses is based upon [KE Emu](https://emu.kesoftware.com/) and everyone who's had the misfortune of having to use it knows that it's literally _dinosaur_ software - it wouldn't look out of place in the year 1999 and again, the actual (poor) performance of it is the far bigger problem. I guess by 2025 the museum might replace it, if there's sufficient funding and the political issues keeping it in place are successfully navigated. To hear just how much everyone at the museum knows what I'm talking about; listen to the knowing laughter in the audience when I describe the NHM's KE Emu database as "terrible" in my SciFri talk video below (from about 3.49 onwards):

https://youtu.be/RzTzKFjkRcM?t=3m43s

Given the above, perhaps now you can better understand my astonishment and sincere praise I feel is due for the team behind the still relatively new online NHM Data Portal at: [http://data.nhm.ac.uk/](http://data.nhm.ac.uk/)

The new Data Portal is flipping brilliant. [Ben Scott](http://www.benscott.co.uk/) is the genius behind it all - the lead architect of the project. Give that man a pay raise, ASAP!

He's successfully implemented the open source [CKAN](http://ckan.org/) software, which itself incidentally is maintained by the Open Knowledge Foundation (now known simply as [Open Knowledge](https://okfn.org/)). This is the same software solution that both the [US](http://www.data.gov/) and [UK](https://data.gov.uk/) governments use to publish their open government data. It's a good, proven, popular design choice, it scales, and I'm pleased to say it works really well for both casual users and more advanced users. This is where the title of post comes in...

**The NHM Specimen Records now have an API and this is bloody brilliant**

In my text mining project to [find NHM specimens in the literature](http://rossmounce.co.uk/2015/05/19/text-mining-for-museum-specimen-identifiers/), and link them up to the NHM's official specimen records, it's vitally important to have a reliable, programmatic web service I can use to lookup tens of thousands of catalogue numbers against. If I had to copy and paste-in each one e.g. "[BMNH(E)1239048](http://data.nhm.ac.uk/specimen/5ad66021-5834-4897-a058-11afd4c2be8c)" _manually_, using a GUI web browser my work simply wouldn't be possible. I wouldn't have even started my project.

Put simply, the new Data Portal is a massive enabler for academic research.

To give something back for all the usage tips that Ben has been kindly giving me (thanks!), I'd thought I'd use this post to describe how I've been using the NHM Data Portal API to do my research:

At first, I was simply querying the database from a local dump. One of the many great features of the new Specimen Records database at the Data Portal, is that the portal enables you to download the _entire_ database as a single plain text table: over 3GB's in size. Just click the "Download" button, you can't miss it! But after a while, I realised this approach was impractical - my local copy after just a few weeks was significantly out of date. New specimen records are made public on the Data Portal every week, I think!

So, I had to bite the bullet and learn how to use the web API. Yes: it's a museum with an API! _How cool is that?_ There really aren't many of those around at the moment. This is cutting-edge technology for museums. The [Berkeley Ecoinformatics Engine](https://ecoengine.berkeley.edu/researchers/) is one other I know of. Among other things it allows API access to geolocated specimen records from the Berkeley Natural History Museums. Let me know in the comments if you know of more.

The basic API query for the NHM Data Portal Specimen Records database is this:


    http://data.nhm.ac.uk/api/action/datastore_search?resource_id=05ff2255-c38a-40c9-b657-4ccb55ab2feb&q=Archaeopteryx


That doesn't look pretty, so let me break it down into meaningful chunks.


    http://data.nhm.ac.uk/api/action/datastore_search

    +

    ?resource_id=05ff2255-c38a-40c9-b657-4ccb55ab2feb

    +

    &q=Archaeopteryx




The first part of the URL is the base URL and is the typical [CKAN DataStore Data API](http://docs.ckan.org/en/ckan-1.7.2/datastore-api.html) endpoint for data search. The second part specifies which exact database on the Data Portal you'd like to search. Each database has it's own 32-digit [GUID](https://en.wikipedia.org/wiki/Globally_unique_identifier) to uniquely identify it. There are currently 25 different databases/datasets available at the NHM Data Portal including [data from the PREDICTS](http://data.nhm.ac.uk/dataset/predicts-site-level-summary-biodiversity-and-pressure-data) project, assessing ecological diversity in changing terrestrial systems. The third and final part is the specific query you want to run against the specified database, in this case: "Archaeopteryx". This is a simple search that queries across all fields of the database, which may be too generic for many purposes.

This query will return 2 specimen records in [JSON](https://en.wikipedia.org/wiki/JSON) format. The output doesn't look pretty to human eyes, but to a computer this is cleanly-structured data and it can easily be further analysed, manipulated or converted.

**More complex / realistic search queries using the API**

The simple search queries across all fields. A more targeted query on a particular field of the database is sometimes more desirable. You can do this with the API too:


    http://data.nhm.ac.uk/api/action/datastore_search

    +

    ?resource_id=05ff2255-c38a-40c9-b657-4ccb55ab2feb

    +

    &filters={"catalogNumber":"PV P 51007"}




In the above example I have filtered my API query to search the "catalogNumber" field of the database for the exact string "[PV P 51007](http://data.nhm.ac.uk/specimen/8076702a-2f26-4c74-be15-b0225b472dce)"

This isn't very forgiving though. If you search for just "51007" with this type of filter you get 0 records returned:


    http://data.nhm.ac.uk/api/action/datastore_search?resource_id=05ff2255-c38a-40c9-b657-4ccb55ab2feb&filters={22catalogNumber%22:%2251007%22}


So, the kind of search I'm actually going to use to lookup my putative catalogue numbers (as found in the published literature) via the API, will have to make use of the more complex [SQL](https://en.wikipedia.org/wiki/SQL)-query style:


    http://data.nhm.ac.uk/api/action/datastore_search_sql

    +

    ?sql=SELECT%20*%20FROM%20%2205ff2255-c38a-40c9-b657-4ccb55ab2feb

    +

    "%20WHERE%20"catalogNumber"%20LIKE%20%27%2551007%27




This query returns 19 records that contain at least partially, the string '51007' in the catalogNumber field. Incidentally, you'll see if you run this search that 3 completely different entomological specimen records share the exact same catalogue number: "BMNH(E)251007":

[_Thamastes dipterus_ Hagen, 1858](http://data.nhm.ac.uk/specimen/9e9baedd-a58c-46b9-9c25-3fa92b83f66e) (Trichoptera, Limnephilidae)

[_Contarinia kanervoi_ Barnes, 1958](http://data.nhm.ac.uk/specimen/0231a94d-8375-4084-947f-5cdc7b205757) (Diptera, Cecidomyiidae)

[_Sympycnus peniculitarsus_ Hollis, D., 1964](http://data.nhm.ac.uk/specimen/89014778-1568-4460-b795-f0bb9b9038fa) (Diptera, Dolichopodidae)

NHM Catalogue numbers are unfortunately far from uniquely identifying but that's something I'll leave for the next post in this series!

Isn't the NHM Data Portal amazing? I certainly think it is. Especially given what it was like before!
