---
layout: post
title: File Structure & BEM - Block, Element, Modifier
fullview: true
---

BEM sets design components as pieces, at the same time giving sass a more architectual presedense in code maintanibilty and structure.

config - code that doesn't create any styles. None of this code gets styled
 - _colors.scss
 - _grids.scss
 - _mixins.scss
 - _breakpoints.scss

Global - site wide partials MAIN content area - whatever content editors are putting in wysiwyg
- _typography
- _extendables - clearfix
- _forms

Vendor - This is for third-pary libraries and module specific styles. Also if you use the magic module. Think override.
 - _lightbox.scss
 - _leaflet.scss

components - Each user interface gets it's own partial file.
  - _person.scss
  - _inside-ucsf.scss

layout - box model properties
  _l-header.scss
  _l-masthead.scss
  _article.scss

BEM

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

semantic panels

