---
layout: post
title: Installation
categories: [general, setup, demo]
tags: [demo, dbyll, dbtek, setup]
fullview: true
---
<img class="gob-dance" src="{{ site.baseurl }}/assets/media/gob-car-dance.gif"/>
<p>For Linux and OS X folks, depending on your setup, you may or may not need to install gems under the sudo user. For example, if you are using RVM, you won't need to install your gems under the sudo user.</p>

<p>For Sass/Compas to run on your computer ruby is needed.</p>

###OSX
<ol>
  <li>Open up terminal.</li>
  <li><pre><code>$ gem install compass</code></pre></li>
</ol>

<h3>Windows</h3>
<p>Make sure to get Ruby 1.9.3-p545 version and
make sure to check add ruby executibles on install.</p>
<ol>
  <li>Install the <a href="http://rubyinstaller.org/" target="_none">ruby installer.</a>
  </li>
  <li>Open up command prompt.</li>
  <li><pre><code>$ gem install compass</code></pre></li>
</ol>



<h3>Linux</h3>

<ol>
  <li>Open terminal</li>
  <li>Enter <pre><code>$ irb</code></pre> If you get an error move on to next step, if not enter <pre><code>$ exit</code></pre> and go to step 4</li>
  <li>Install ruby so you can install compass/sass <pre><code>$ sudo apt-get install ruby</code></pre>or
<pre><code>$ sudo yum install ruby</code></pre> or any other package manager you may have. After installation move on to the next step.
  </li>
  <li>Enter <pre><code>$ sudo gem install compass</code></pre></li>
</ol>
