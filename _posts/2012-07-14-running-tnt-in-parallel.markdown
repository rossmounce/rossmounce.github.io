---
author: rmounce
comments: true
date: 2012-07-14 10:03:47+00:00
layout: post
link: http://rossmounce.co.uk/2012/07/14/running-tnt-in-parallel/
slug: running-tnt-in-parallel
title: Running TNT in parallel
wordpress_id: 268
categories:
- Conferences
- Phylogenetics
- TNT
---

Building upon the instructions given [here](http://tnt.insectmuseum.org/index.php/Running_tnt_in_parallel) and [here](http://www.zmuc.dk/public/phylogeny/tnt/) I thought I'd write up one of the many useful things Pablo Goloboff kindly taught us at the TNT scripting workshop after the Hennig XXXI meeting.

[![](http://rossmounce.co.uk/wp-content/uploads/2012/07/workshop.jpg)](http://rossmounce.co.uk/wp-content/uploads/2012/07/workshop.jpg)

It's actually not the easiest thing to setup if you're using [Ubuntu](http://www.ubuntu.com/)... Pablo had to help me do it - I would never have got it up and running on my own.

THE FOLLOWING INSTRUCTIONS ASSUME YOU'RE USING UBUNTU ON A MULTICORE MACHINE

You'll need to install the _pvm _package either from the repositories with

`sudo apt get install pvm`

or download and compile [from source](http://www.netlib.org/pvm3/index.html)

It's actually better to compile from source because the pvm package in the Ubuntu repositories is out of date - they provide only version 3.4.5, whilst the latest version of pvm, released way back in 2009 is 3.4.6 ! I guess the packaging team have other priorities...

Then you'll need to configure pvm on your machine:



	
  * edit your bashrc file  `nano ~/.bashrc`  and insert this line:


export PVM_ROOT=/usr/lib/pvm3

save & close the bashrc file. Now  `source ~/.bashrc` and then test the path with `echo $PVM_ROOT` this should now return

/usr/lib/pvm3



	
  * in your user home directory (for me this is /home/ross/ ) create a plaintext file called hostlist (the exact name doesn't matter but remember it) and write one line within this file:


rossnetbook ep=/usr/bin/

(replace 'rossnetbook' with your computer hostname - if you're not sure what this is then `nano /etc/hostname` will tell you) save and close this file.



	
  * now start pvm from your user home directory with `pvm hostlist`  this tells pvm your hostname and the path. Unfortunately you'll need to start-up pvm this way every time you restart your computer. Perhaps there's a better way? Let me know if so...


Finally, make sure you've copied the 64-bit TNT binary to both /usr/bin/ & to your user home directory and make sure that they're executable.

Now you should be ready to go...

if you get an error message like this from TNT:


<blockquote>tnt*>ptnt begin ajob2 2 = mult 5; return ; ptnt wait . ;
Macro language is ON
Macros: 50.5 Kb in use, 51.8 Kb free
libpvm [pid7539] /tmp/pvmd.1000: No such file or directory
libpvm [pid7539] /tmp/pvmd.1000: No such file or directory
libpvm [pid7539] /tmp/pvmd.1000: No such file or directory
libpvm [pid7539]: pvm_config(): Can't contact local daemon

Can't enter parallel interface (make sure PVM is running)</blockquote>


you've probably forgotten to start pvm with `pvm hostlist`

see the video I uploaded below for demonstration of the speed-up possible by performing tasks in parallel:



the video shows me performing a simple search on the zilla dataset of Chase et al. (1993) using traditional heuristic settings (60 reps) performed first in serial, then in parallel (starting after 2:00) 20 reps x 3 slaves.

100 seconds for search 1, down to just 48 seconds for search 2 (in parallel). YMMV

Neither of these searches found the shortest length trees btw!

Commands:
`mxram 100;` /* increase memory */
`p zilla.tnt;` /* read in the data */
`hold 20000;` /* increase the maximum number of trees held */
`mult 60;` /* perform a traditional search with 60 replications */
`le;` /* tree lengths */

/* parallel tnt job, called 'ajob' using 3 slaves performing 'mult 20' on each slave */ 
`ptnt begin ajob 3 = mult 20; return ; ptnt wait . ;`

basically just insert what you want your slaves to do in between the '=' and the return; commands.

`ptnt get ajob;` /* get data back from slaves to master */


This was just the tip of the iceberg of the course. I can't even begin to write-up the rest of the course in this much detail! But I hope this helps...

[caption id="attachment_285" align="aligncenter" width="444"][![](http://rossmounce.co.uk/wp-content/uploads/2012/07/workshop2.jpg)](http://rossmounce.co.uk/wp-content/uploads/2012/07/workshop2.jpg) many many thanks Pablo, and all the organisers of this workshop AND the conference - it was *much* appreciated[/caption]


