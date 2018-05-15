---
layout: post
title: Getting started with a little bit of SVG  
categories: [code]
date: 2018-05-14 17:07:19
comments: true
---

Ok so the SVG based thumbnail creation wasn't terribly challenging. All I had to do was initialize an SVG file in the img/ folder for this project, and point the 'avatar' field to the file in the `_config.yml` file.  
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

Then I figured it might be cool to start by editing previously generated SVG images - [how about DNA?](http://petercollingridge.appspot.com/draw-dna). So I used this website to generate a rendering of ATGC, and downloaded the SVG in the /img folder.  

