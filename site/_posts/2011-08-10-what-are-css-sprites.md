---
layout: post
title: What are CSS Sprites?
---

{{ page.title }}
================


<style type='text/css' data-linked='sprite-demo'>

.sprite { background: url('icon.png') no-repeat top left; padding-left: 20px; line-height: 16px;  } 
.sprite.delete { background-position: 0px 0px;  } 
.sprite.group { background-position: 0px -26px;  } 
.sprite.help { background-position: 0px -52px;  } 

</style>

<style type='text/css' data-linked='nosprite-demo'>

.nosprite { padding-left: 20px; line-height:16px; background-repeat: no-repeat; }
.nosprite.help { background-image: url('help.png'); }
.nosprite.delete { background-image: url('delete.png'); }
.nosprite.group { background-image: url('group.png'); }

</style>

<p>
CSS Spriting is a technique used to limit the number of HTTP requests generated by a web page.  This is done by combining multiple images into one image and using the CSS <code>background-position</code> property.
</p>

<h3>An Example - Three Plain Links</h3>

<p>
Let's imagine that you have some links on your page:
</p>

<section class='demo viewsource'>
<a href='#'>Delete an item</a> |
<a href='#'>Contact us</a> |
<a href='#'>Need help?</a>
</section>

<h3>Three Links, With Style</h3>

<p>
Your links look great, but you decide spice it up a little bit with some images.  You find three icons.  Here they are:
</p>

<section class='demo images viewsource'>
<img src='delete.png' /> <img src='group.png' /> <img src='help.png' />
</section>

<p>
Using CSS and the images, you set the background and put a little bit of padding on the left to add some space before the text starts.  Your links now look like this:
</p>

<section id='nosprite-demo' class='demo viewsource'>
<a href='#' class='nosprite delete'>Delete an item</a> |
<a href='#' class='nosprite group'>Contact us</a> |
<a href='#' class='nosprite help'>Need help?</a>
</section>

<p>
Looks perfect!  Only one problem.  There are three images.  For each image, a web browser needs to open an HTTP connection to download the image.  Some browsers can only have 2 connections open at once, so this could slow your page down quite a bit.
</p>

<h3>Three Links, With CSS Sprites</h3>

<p>
You can <a href='<?=$docroot?>'>combine all these images</a> using a <a href='<?=$docroot?>'>CSS sprite generator</a>.  Done?  OK, now we have a nice combined image:
</p>

<section class='demo images viewsource'>
<img src='icon.png' />
</section>

<p>
We can't just set the background image on all of them to icon.png.  It would look like this:
</p>

<section class='demo viewsource'>
<a href='#' class='sprite'>Delete an item</a> |
<a href='#' class='sprite'>Contact us</a> |
<a href='#' class='sprite'>Need help?</a>
</section>

<p>
<strong>That doesn't look quite right...</strong> See that setting the background image to "top left" causes each link to display the top image in our sprite (in this case, the delete image).  This is the extra work we need to do for sprites.  We need to use the offsets to position the background image properly: 
</p>

<section id='sprite-demo' class='demo viewsource'>
<a href='#' class='sprite delete'>Delete an item</a> |
<a href='#' class='sprite group'>Contact us</a> |
<a href='#' class='sprite help'>Need help?</a>
</section>

<!--
<h3>Ready for more?</h3>
<p>
The article <a href='../how-to-use-css-sprites'>How To Use CSS Sprites</a> goes into more detail about a workflow to simplify your CSS sprite usage. 
</p>

<p>
If you want to <a href='<?=$docroot?>'>generate CSS sprites</a>, check out Instant Sprite.
</p>
-->

<h3>More resources</h3>
<p>Here are some popular CSS Sprite articles with more explanations, examples, and links:</p> 

<ul>
<li><a href='http://www.alistapart.com/articles/sprites'>A List Apart</a></li>
<li><a href='http://www.smashingmagazine.com/2009/04/27/the-mystery-of-css-sprites-techniques-tools-and-tutorials/'>Smashing Magazine</a></li>
<li><a href='http://developer.yahoo.com/performance/rules.html'>Yahoo Developer Network</a></li>
<li><a href='http://code.google.com/speed/page-speed/docs/rtt.html#SpriteImages'>Google Page Speed</a></li>
</ul>
