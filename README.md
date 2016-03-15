# include-media-grid
An include-media plugin for generating grid classes based on the flex display property

## Introduction
This plugin generates classes for a grid system based on a number of subdivisions specified by the user, and taking into account all the breakpoints defined by include-media.

*Example:*

```scss
@import 'include-media';
@import 'include-media-grid';

// Generating grid classes
@include im-grid-columns(1, 2);
```



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

