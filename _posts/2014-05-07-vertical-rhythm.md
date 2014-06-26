---
layout: post
title: Vertical Rhythm
fullview: true
---

<img src="{{ site.baseurl }}/assets/media/incremental_1.gif" />

<pre class="prettyprint lang-scss"><code>

  $base-font-size: 14px;
  $base-line-height: 21px;

  @include establish-baseline;

  body {
    @include adjust-font-size-to($base-font-size);
  }

  h1 {
    @include adjust-font-size-to(31px);
  }

  /* This translates to */

  html {
    font-size: 87.5%;
    line-height: 1.5em;
  }

  body {
    font-size: 1em;
    line-height: 1.5em;
  }

  h1 {
    font-size: 2.21429em;
    line-height: 1.35484em;
  }


</code></pre>
