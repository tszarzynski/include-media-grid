# include-media-grid
An include-media plugin for generating grid classes based on the flex display property

## Introduction
This plugin generates classes for a grid system based on a number of subdivisions specified by the user, and taking into account all the breakpoints defined by [include-media](https://github.com/eduardoboucas/include-media).

```scss

@import 'include-media';
@import 'include-media-grid';

$breakpoints: (phone: 480px, tablet: 768px, desktop: 1024px);

// Grid class name
$im-grid-class: 'grid';
// Cell class name
$im-grid-cell-class: 'grid-cell';
// Setting gutters
$im-grid-gutter-size: 20px;
// Optionally include max-width to fix IE issues
$im-grid-include-max-width: false !default;
// Generating grid classes for 1, 2 and 4 column layouts
@include im-grid-columns(1, 2, 4);
```

#### Basic Grids:
The grid cells below do not specify any widths, they just naturally space themselves equally and expand to fit the entire row. They’re also equal height by default.

```html
<div class="grid">
  <div class="grid-cell">1/2</div>
  <div class="grid-cell">1/2</div>
</div>
<div class="grid">
  <div class="grid-cell">1/3</div>
  <div class="grid-cell">1/3</div>
  <div class="grid-cell">1/3</div>
</div>
<div class="grid grid--flex-cells">
  <div class="grid-cell">Full-height, even when my content doesn't fill the space.</div>
  <div class="grid-cell">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum mollis velit non gravida venenatis. Praesent consequat lectus purus, ut scelerisque velit condimentum eu. Maecenas sagittis ante ut turpis varius interdum. Quisque tellus ipsum, eleifend non ipsum id, suscipit ultricies neque.</div>
</div>
```

#### Gutters
```html
<!-- With gutters -->
<div class="grid grid--gutters">
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
</div>
```

#### Individual Sizing
When equal widths aren’t what you want, you can add sizing classes to individual cells. Cells without sizing classes simply divide up the remaining space as normal.

```html
<!-- Force cell to be always a full width single column -->
<div class="grid" >
  <div class="grid-cell">auto - 1/2</div>
  <div class="grid-cell">auto - 1/2.</div>
  <div class="grid-cell grid-cell--1-1">Always single column!!!</div>
</div>
```

#### Weight
You can change the way the cells size themselves, by modifying `flex-grow` property.

```html
<!-- With gutters -->
<div class="grid grid--gutters">
  <div class="grid-cell grid-cell--light">Half the weight of default column.</div>
  <div class="grid-cell"></div>
</div>
```

```html
<!-- With gutters -->
<div class="grid grid--gutters">
  <div class="grid-cell grid-cell--heavy">Twice the weight of default column.</div>
  <div class="grid-cell"></div>
</div>
```

#### Responsive
Responsive Grids work by adding media classes to the Grid cells or containers. When those media values are met, the grids automatically adjust accordingly.

```html
<!-- 1 column on mobile phones. 2 columns on tablets. 4 on desktop devices -->
<div class="grid grid--1-1@phone grid--1-2@tablet grid--1-4@desktop">
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
</div>

<!-- Full-width up to desktop breakpoint -->
<div class="grid grid--full grid--1-4@desktop">
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell grid-cell--1-1@dekstop"></div>
  <div class="grid-cell grid-cell--1-1">Always single column!!!</div>
</div>

<!-- Individual sizing -->
<div class="grid grid--1-1@phone grid--1-2@tablet grid--1-4@desktop">
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell grid-cell--1-1">Always single column!!!</div>
</div>
```

#### Auto grids
You can avoid adding `grid-cell` to children of the grid by using the `grid--auto` class. All children elements will be treated as a `grid-cell`.

```html
<!-- No need for grid-cell  -->
<div class="grid grid--auto">
  <div>same row</div>
  <div>same row</div>
  <div>same row</div>
  <div>same row</div>
</div>
```

If you need your grid items to fit a specific number of columns, you can use `grid--auto-{columnNumber}`. Any column set generated with im-grid-columns is usable. Responsive grids are also usable.

```html
<!-- No need for grid-cell, two columns per row  -->
<div class="grid grid--gutters grid--auto grid--auto-2@tablet grid--auto-4@desktop">
  <div>first row on desktop, first row on tablet</div>
  <div>first row on desktop, first row on tablet</div>
  <div>first row on desktop, second row on tablet</div>
  <div>first row on desktop, second row on tablet</div>
</div>
```

#### Alignment Features

```html
<!-- Top-aligned Grid Cells -->
<div class="grid grid--top">
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
</div>

<!-- Bottom-aligned Grid Cells -->
<div class="grid grid--top">
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
</div>

<!-- Vertically Centered Grid Cells -->
<div class="grid grid--center">
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
  <div class="grid-cell"></div>
</div>
<!-- Mixed Vertical Alignment -->
<div class="grid grid--top">
  <div class="grid-cell"></div>
  <div class="grid-cell grid-cell--center"></div>
  <div class="grid-cell grid-cell--bottom"></div>
</div>
```

More examples coming soon. See source files for more options.

> It's recommended to use this plugin along with **autoprefixer** to maintain cross-browser [support] (http://caniuse.com/#feat=flexbox).

## Requirements
* Sass >= 3.4.x
* [include-media](https://github.com/eduardoboucas/include-media)

## Installation
- **Manually:** Download [this file](https://raw.githubusercontent.com/tszarzynski/include-media-grid/master/_include-media-grid.scss) and import it into your Sass project
- **npm:** Run `npm install include-media-grid`
- **Bower:** Run `bower install include-media-grid`

## Inspiration
- [philipwalton.github.io/solved-by-flexbox/demos/grids](http://philipwalton.github.io/solved-by-flexbox/demos/grids/)
- [github.com/eduardoboucas/include-media-columns](https://github.com/e duardoboucas/include-media-columns)

## Author
[Tomasz Szarzynski](http://tmasz.com)

