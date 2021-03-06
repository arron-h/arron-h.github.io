---
layout: post
title: ProTrawler
tags: cycling software javascript python
category: software
---

First post, first project. I’ll start with the ‘why?’. A few months ago I was pondering what the average weight and height of a professional cyclist was.
A few websites had some unsupported claims but there was nothing concrete and as an engineer, this disturbed me.

I knew Wikipedia had a weight and height for 90% of the pro peleton, which isn’t 100% reliable but it would still provide me with a good average. So, after a quick
trial run, I set about creating a python script which would first get a list of riders in the current season (turns out Wikipedia has a page for this too), and then
grab each rider’s page, process it and eventually work out my magic average. This actually worked pretty well and I soon had a full ‘database’ of riders and their weights,
heights, team and representative country. Because I love graphs, tables and data I thought it would be a good idea to extend this simple python script to generate a javascript
‘fixture’ object for use with a simple web app to display my data. The result of this work is [ProTrawler](http://www.arronhartley.com/protrawler/) and you can view all of the
lovely source code over at [my github page](http://www.github.com/arron-h/).

Now I’ll get more technical and describe my approach and the technicalities involved.

### The python ‘trawler’ script


### The web app
I chose [Ember](http://www.emberjs.com) as a Javascript MVC framework because it’s the only one I’d used previously and it seemed OK. In retrospect I would have chosen
[AngularJS](http://www.angularjs.com) because it’s better documented, easier to use and generally less ghey. Although please not *I do not encourage the use of Javascript*.

In order to ‘scaffold’ the

Writing the web app was fairly simple as it’s just one page, and basically a massive fixture which is generated by the python script. After I got the basic table of riders
displaying I realised it would be really useful to be able to sort the columns. This proved more difficult and required copious amounts of JQuery (urgh). Eventually I got it
working but another problem arose: JQuert ‘column sort’ pretty much falls-over on a 500-row table. Because this is client-side Javascript as well, it depends on the user’s
system specification and my MacBook Pro was having trouble so I decided I needed to do something about it. Turns out psuedo pagination was the solution. Limiting the displayble
results to 50 riders (and in reality, if one sorts the columns, 50 results is more that enough) solved this problem and allowed the sort functionality to be usable and interactive.

The second ‘difficult’ component was the bar graphs that can be seen at the bottom of the page. I used D3 to assist in the generation of these graphs and whilst D3 is quite popular
amongst the web developer community, it is not particularily intuative to use. Never-the-less, plentiful examples abound the internets so I managed to find some sample code to
tailor to my requirements.

Once the graph

