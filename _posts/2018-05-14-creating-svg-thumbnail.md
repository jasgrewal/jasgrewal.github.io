---
layout: post
title: Getting started with a little bit of SVG  
categories: [code, SVG, Chrome]
date: 2018-05-14 17:07:19
comments: true
---

Ok so the SVG based thumbnail creation wasn't terribly challenging. All I had to do was initialize an SVG file in the img/ folder for this project, and point the 'avatar' field to the image name, in the `_config.yml`.  

The tricky part, I guess, is documenting what I did.   

<!--more-->

Here's the shitty little SVG code chunk I started out with, just to get my bearings.  
{% highlight svg %}
{% raw %}
<svg width="100%" height="100%" version="1.1" xmlns="http://www.w3.org/2000/svg">

<defs>
<linearGradient id="fill" x1="0%" y1="0%" x2="0%" y2="100%">
<stop offset="0%" style="stop-color:rgb(224,224,224);stop-opacity:1"/>
<stop offset="100%" style="stop-color:rgb(153,153,153);stop-opacity:1"/>
</linearGradient>
</defs>

<path d="M 0 0 L 64 0 L 32 64 z" stroke="colourname" fill="url(#fill)"/>

</svg>
{% endraw %}}
{% endhighlight %}

Trying to edit this directly in the SVG code, I eventually realised it will take me more time to build a fancy avatar than the time it took me to set up the website.  
...the lazy CS student awakens....
So then I figured it might be cool to start by editing previously generated SVG images - [how about DNA?](http://petercollingridge.appspot.com/draw-dna). I used this website to generate a rendering of ATGC, and downloaded the SVG in the /img folder. Note I had to modify the dimensions of the generated SVG so the viewing window was the exact size as the desired graphics, and that the relative coordinates of the image were relative to (0,0). This made it slightly easier to co-locate the avatar versus the rest of the Sidebar viewing pane.  

### Matching the colour palette  
In the initial version of the DNA, the color palette for the A, T, C, and G's was defined thus:  
A: 
T: f79646
G: 4bacc6
C: 9bbb59

I've always been a fan of the purple and gold palette, and the pink in this Jekyll template complements both these colours. Therefore I wanted to maintain the same color tones in the avatar. Conveniently, I have this nice [plugin that picks up the colours in a given page](https://chrome.google.com/webstore/detail/colorzilla/bhlhnicpbhignbdhedgjhgdocnmhomnp?hl=en) and copies the HEX code to your clipboard. So with a few extra clicks with ColorZilla, I had the following color palette:  
A: #8D80DA
T: #c28087
G: #7066ae
C: #F3A0A9

Since I had 4 bases and I didn't want to excessively crowd the colors, I decided to use a different hue of A's color for G, and C's to T's, to reflect the most common event of cytosine deamination (whereby C loses an amino group to form uracil, U). As I keep on forgetting, this will eventually turn a C-G ds-bond into a T-A ds-bond in one mature daughter DNA after a round of replication.  

