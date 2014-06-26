---
layout: post
title: SASS/COMPASS Introduction
fullview: true
---
<img class="shia-magic" src="{{ site.baseurl }}/assets/media/shia-magic.gif"/>

<p>SASS stands for syntactically awesome style sheets. It is a preprocessor that compiles into css. This allows a person to use features such as variables, nesting, mixins, inheritence and other advanced coolness that isn't in css. Pretty much sass makes writing css fun.</p>

<p>Compass is a sass library that extends the functionality of sass.</p>

<h2>Variables</h2>

<p>Variables in sass are a way to store information. Generally in a sass project variables will be assigned typefaces, colors, or dimensional defaults that have been set for your project. Sass variables allow a user to make a change from a singular point instead of finding every single selector. Ex. "Hey Bob I don't like this main font color can you change it to this light blue."</p>

<pre class="prettyprint lang-scss">
  <code>
  $main-font: Helvetica, Arial, "Lucida Grande", sans-serif;
  $other-font: $main-font;
  </code>
</pre>

<pre class="prettyprint lang-scss">
  <code>
  $full-width: $body-width + $sidebar-width;
  $something-block: $full-width / 2;
  </code>
</pre>

<h2>Nesting</h2>

<p>Have you ever looked through a 2000 line file of css searching for a specific class or id that wasn't formatted correctly and maybe worse inline on a html file? Maybe even in this file the styles were repeated and repetitive. Nesting in sass is an answer to all of this and it makes editing and upkeeping your css so much easier.</p>

<pre class="prettyprint lang-scss"><code>
  nav {

    ul {
      margin: 0;
      padding: 0;
      list-style: none;

      li {
        display: inline-block;

         a {
          display: block;
          padding: 6px 12px;
          text-decoration: none;
        }
      }
    }
  }


</code></pre>

<h2>Mixins</h2>

<p>Compass provides many mixins to make writing css and expecially css3 easier. Not only easy but cross browser compatible.</p>

<p>Take this example:</p>

<pre class="prettyprint lang-scss"><code>
  .box {
    @include border-radius(10px);  /* This translates into what is below */
  }


  .box {
    -moz-border-radius: 10px;
    -webkit-border-radius: 10px;
    -ms-border-radius: 10px;
    -o-border-radius: 10px;
    -khtml-border-radius: 10px;
    border-radius: 10px;
  }


</code></pre>
<h2>Extend</h2>

<p>Extend allows you to do exactly what it says. It allows you to extend css properties to other selectors. Once again keeping things DRY and clean.</p>

<pre class="prettyprint lang-scss"><code>
  .main {
    background: red;
    padding: 20px;
    border: 1px dotted green;
  }

  .cool-thing {
    @extend .main; /* Now .cool-thing has .main's properties. */
    background: blue; /* Changes one of the extended properties to blue */
  }


</code></pre>
