# include-media-grid
An include-media plugin for generating grid classes based on the flex display property

## Introduction
This plugin generates classes for a grid system based on a number of subdivisions specified by the user, and taking into account all the breakpoints defined by include-media.

*Example:*

```scss
$breakpoints: (phone: 480px, tablet: 768px, desktop: 1024px);
@import 'include-media';
@import 'include-media-grid';

// Setting gutters
$im-grid-gutter-size: 20px;
// Optionally include max-width to fix IE issues
$im-grid-include-max-width: false !default;
// Generating grid classes
@include im-grid-columns(1, 2, 4);
```

*Usage:*

```html
<!-- Simple grid. 1 column on mobile phones. 2 columns on tablets. 4 on desktop devices -->
<div class="grid grid--1-1@phone grid--1-2@tablet grid--1-4@desktop">
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
</div>

<!-- With gutters -->
<div class="grid grid--gutters grid--1-1@phone grid--1-2@tablet grid--1-4@desktop">
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
</div>

<!-- Force cell to be always a full width single column -->
<div class="grid grid--gutters grid--full grid--1-2@tablet" >
  <div class="grid-cell">Full on phone. Half on tablet.</div>
  <div class="grid-cell">Full on phone. Half on tablet.</div>
  <div class="grid-cell">Full on phone. Half on tablet.</div>
  <div class="grid-cell">Full on phone. Half on tablet.</div>
  <div class="grid-cell grid-cell--1-1">Always single column!!!</div>
</div>
```

More examples coming soon. See source files for more options.

## Requirements
* Sass >= 3.4.x
* [include-media](https://github.com/eduardoboucas/include-media)

## Installation
- **Manually:** Download [this file](https://raw.githubusercontent.com/tszarzynski/include-media-grid/master/_include-media-grid.scss) and import it into your Sass project
- **npm:** Run `npm install include-media-grid`
- **Bower:** Run `bower install include-media-grid`

##Inspiration
- [philipwalton.github.io/solved-by-flexbox/demos/grids](http://philipwalton.github.io/solved-by-flexbox/demos/grids/)
- [github.com/eduardoboucas/include-media-columns](https://github.com/e duardoboucas/include-media-columns)

## Author
[Tomasz Szarzynski](http://tmasz.com)

