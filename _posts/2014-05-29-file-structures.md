---
layout: post
title: File Structure & BEM - Block, Element, Modifier
fullview: true
---
BEM and SMACCS sets design components as pieces, at the same time giving sass a more architectual presence while keeping code maintainable and structured.

<h3>BEM</h3>

<pre class="prettyprint lang-scss"><code>
  sass/
  |-- components # Each user interface w/ partial
  |   |-- _talk-block.scss
  |-- config
  |   |-- _breakpoints.scss
  |   |-- _colors.scss
  |   |-- _grids.scss
  |   |-- _minins.scss
  |-- global # site wide partials MAIN content area
  |   |-- _extendables.scss
  |   |-- _forms.scss
  |   |-- _typography.scsss
  |-- layout # box model properties
  |   |-- _l-header.scss
  |   |-- _l-masthead.scss
  |-- vendor # This is for third-pary libraries/module css
  |   |-- _lightbox.scss
  |
  `--- screen.scss


</code></pre>

<pre class="prettyprint lang-scss"><code>
  .tabs {} /* Block = Componetn) */
  .tabs__field {} /* Element */
  .tabs--full {} /* Modifier */

  .person {}
  .person__hand {}
  .person--female {}
  .person--female__hand {}
  .person__hand--left {}

  .inside-ucsf {
    color: $white;
    @extend %block--border;

    .inside-ucsf__button {
      background: $grey;
      @include box-shadow(#000 0 1px 2px, #fff 0 1px inset);
    }
  }

  .inside-ucsf-special {
    @extend .inside-ucsf;
    background-color: pink;
    .inside-ucsf-special__button{
      @extend .inside-ucsf__button;
    }
  }


</code></pre>



<h4>SMACCS</h4>

<pre class="prettyprint lang-scss"><code>
  sass/
  |
  |-- modules/              # Common modules
  |   |-- _all.scss         # Include to get all modules
  |   |-- _utility.scss     # Module name
  |   |-- _colors.scss      # Etc...
  |   ...
  |
  |-- partials/             # Partials
  |   |-- _base.sass        # imports for all mixins + global project variables
  |   |-- _buttons.scss     # buttons
  |   |-- _figures.scss     # figures
  |   |-- _grids.scss       # grids
  |   |-- _typography.scss  # typography
  |   |-- _reset.scss       # reset
  |   ...
  |
  |-- vendor/               # CSS or Sass from other projects
  |   |-- _colorpicker.scss
  |   |-- _jquery.ui.core.scss
  |   ...
  |
  `-- main.scss            # primary Sass file


</code></pre>

I've included a boilerplate at UCSF Drupal's Github. Find a place in your file system to store this repository. Install the files by:

<pre><code>$ git clone git@github.com:ucsf-drupal/sass-workshop.git
</code></pre>

If that doesn't work for you try:

<pre><code>$ git clone https://github.com/ucsf-drupal/sass-workshop.git</code></pre>

Next switch to the "structure" branch

<pre><code>$ git checkout structure</code></pre>
