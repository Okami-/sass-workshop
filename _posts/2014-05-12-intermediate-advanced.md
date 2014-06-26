---
layout: post
title: Intermediate/Advanced Sass
fullview: true
---

<h3>Mixins</h3>

I would say mixins are one of the most powerful aspects of Sass.

<h5>Clearfix Mixin</h5>

<pre class="prettyprint lang-scss"><code>
  @mixin clearfix() {
    &:before,
    &:after {
      content: "";
      display: table;
    }
    &:after {
      clear:both;
    }
  }


</code></pre>

<h5>Usability</h5>

<pre class="prettyprint lang-scss"><code>
  .mydiv {
    @include clearfix();
  }


</code></pre>

<h5>Css Output</h5>

<pre class="prettyprint lang-scss"><code>
  .mydiv {
    *zoom: 1;
  }

  .mydiv:before, .mydiv:after {
    content: "";
    display: table;
  }

  .mydiv:after {
    clear: both;
  }


</code></pre>

<hr>

Many mixins already come installed with compass already.

Normally a person would have to write out multiple lines of code for css3
things such as border-radius and box-sizing.

<h4>Mixin that resets elements box model</h4>
<h5>Sass....</h5>
<pre class="prettyprint lang-scss"><code>
   .content-box {
    @include box-sizing(content-box);
   }
   .border-box {
    @include box-sizing(border-box); /* box sizing mixin is built into compass */
   }


</code></pre>

<h5>Css Output</h5>
<pre class="prettyprint lang-scss"><code>
  .content-box {
    -webkit-box-sizing: content-box;
    -moz-box-sizing: content-box;
    box-sizing: content-box;
  }

  .border-box {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
  }


</code></pre>

<hr>

Sass also has functions that can be intertwined with mixins.

While the function does the calculation the mixin can be used to make things more uniforn and clean.

Rem is a rising font size that allows scalable text on a global scale. Allowing for media queries with a single rule scaling text for your entire site with just one line of code.

<pre class="prettyprint lang-sass"><code>
    @function calculateRem($size) {
      $remSize: $size / 16px;
      @return $remSize * 1rem;
    }

    /* Mixin uses function to calculate and spit out values assigned to variable */
    @mixin font-size($size) {
      font-size: $size;
      font-size: calculateRem($size);
    }

    /* Usage of mixin */
    p {
      @include font-size(14px);
    }

</code></pre>

<h4>Placeholders and extend</h4>

<pre class="prettyprint lang-sass"><code>
  %checkmark { /* The % sign holds a assigned chunk of code */
    &:after{
      content: "\2713 ";
      margin-left: 1em;
    }
  }

  %message-default {
    @include border-radius(10px);
    border: 1px solid $grey-dark;
    marign: $margins;
    padding: $padding;
    text-align: center;
  }

  /* The extend mixin reuses the code in different places which renders the code. It <b>does not</b> duplicate in the preprocessed css. Allowing cleaner code and faster load times. */

  .message-box {
    @extend %message-default;
    @extend %checkmark;
    background-color: $grey-light;
  }

  .message-box--success {
    @extend %message-default;
    @extend %checkmark;
    background-color: $green;
  }


</code></pre>

