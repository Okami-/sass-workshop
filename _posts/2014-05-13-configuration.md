---
layout: post
title: Play Time
fullview: true
---

The best way to learn sass/compass is to create your own project and go from there.

###Creating a Sass Project

Find a good place on your computer and create a folder called sass-test

CD into that folder with your command line and type

<pre><code>$ compass create</code></pre>

This will create two folders inside your working directory. One called stylesheets and one called sass. The terminal will also spit out some html to paste into your file where you reference your css. Hold off on this step as we will get to that point in a bit. CD into the sass directory and open up screen.scss with your favorite text editor. You'll first notice a import rule importing a reset file. This file is used to normalize margin, padding and other css across the board for all browsers. So definately keep that. If you would like to read more about reset please visit <a href="http://meyerweb.com/eric/tools/css/reset/">meyerweb.com/eric/tools/css/reset/</a>.

Go back to the command line and cd back to your working directory a level above the sass folder. Compass compile has generated a config.rb that tells compass where your stylesheets, images, etc. is. I usually remember where the config.rb is, is where I do compass watch.

<pre><code>$ compass watch</code></pre>

Go ahead and put that command in and compass should start watching your sass file now. This allows for on the fly compiling to normal css. Now that we have compass watching our file(s) we can begin to make changes.

You can also try out commands with
