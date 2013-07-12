gee
===

A minimalistic (un)semantic grid system framework built on top of [LESS](http://lesscss.org).

1. [Introduction](#introduction)
2. [Basic Usage](#basic-usage)
3. [Responsive Grids](#responsive-grids)
4. [Grid Gutters](#grid-gutters)
5. [Pixel-Based Grids](#pixel-based-grids)
6. [Credits](#credits)
7. [License](#license)

Introduction
------------

gee is a percentage-based grid system defaulting to 12 columns. It can be either
used in a semantic way by using LESS mixins or in a traditional class-based
(unsemantic) way.

The basic components are "rows" and "columns" where a row contains one or more
columns. The only requirement is that all columns are children of a row.

Basic Usage
-----------

Download [gee.less](gee.less?raw=1) and import
it into your LESS stylesheet:

```css
@import 'gee.less';
```

### Semantic way

Consider the following HTML structure.

```html
<div class="container">
    <article class="main">...</article>
    <section class="sidebar">...</section>
</div>
```

We can now apply the grid behavior to the elements by using the `.gee-row()`
and `.gee-col()` mixins.

```css
.container {
    .gee-row();
}

.main {
    .gee-col(9);
}

.sidebar {
    .gee-col(3);
}
```

By default, gee uses a 12-column grid. You can adjust the number of columns by
either changing the global variable `@gee-colums` or by passing the number as
second argument to the `.gee-col()` mixin.

```css
@gee-columns: 24;

.main {
    .gee-col(18);
}

.sidebar {
    .gee-col(6);
}

/** OR **/

.main {
    .gee-col(18, 24);
}

.sidebar {
    .gee-col(6, 24);
}
```

### Class-based (unsemantic) way

If you prefer a more traditional approach by using classes in your markup, you
can use the `.gee-generate()` mixin to generate all required classes in your
LESS stylesheet.

The arguments for the mixin are:

1. The number of columns (default is 12)
2. The gutter between the columns in % (default is 0)
3. The prefix for the generated classes (default is gee- which results in
   class names like gee-row, gee-col-12, gee-col-11 etc).

```css
.gee-generate(12, 0, gee-);
```

Here's the full list of generated classes you can use.

```css
.gee-row {}
.gee-col-12 {}
.gee-col-11 {}
.gee-col-10 {}
.gee-col-9 {}
.gee-col-8 {}
.gee-col-7 {}
.gee-col-6 {}
.gee-col-5 {}
.gee-col-4 {}
.gee-col-3 {}
.gee-col-2 {}
.gee-col-1 {}
```

You can now use these classes in your HTML to apply the grid behavior.

```html
<div class="gee-row container">
    <article class="gee-col-9 main">...</article>
    <section class="gee-col-3 sidebar">...</section>
</div>
```

Responsive Grids
----------------

Responsive grids can be simply archieved by adding a little extra code.

### Semantic way

You can change the width of columns based on media queries by using the
`.gee-col-width()` mixin.

```css
.container {
    .gee-row();
}

.main {
    .gee-col(9);
}

.sidebar {
    .gee-col(3);
}

@media (max-width: 767px) {
    .main,
    .sidebar {
        .gee-col-width(12);
    }
}
```

### Class-based (unsemantic) way

Add the following code to your stylesheet to collapse columns to full width on
screens lower than 768px.

```css
@media (max-width: 767px) {
    .gee-row > [class*="gee-col"] {
        width: 100%;
    }
}
```

Grid Gutters
------------

gee can be configured to have gutters between the columns. Gutter widths must be
defined in percent.

### Semantic way

You can define a gutter by either changing the global variable `@gee-gutter` or
by passing the number as third argument to the `.gee-col()` mixin.

```css
@gee-gutter: 2%;

.main {
    .gee-col(9);
}

.sidebar {
    .gee-col(3);
}

/** OR **/

.main {
    .gee-col(9, 12, 2%);
}

.sidebar {
    .gee-col(3, 12, 2%);
}
```

### Class-based (unsemantic) way

Simply pass the gutter width as second argument to the `.gee-generate()` mixin.

```css
.gee-generate(12, 2%);
```

Pixel-Based Grids
-----------------

Sometimes you may have the requirement to use pixel-based column widths.
Custom column sizes can be applied by combining your custom widths with a
generic column.

### Semantic way

Just use the `.gee-col-base()` mixin.

```css
.container {
    .gee-row();
    width: 960px;
}

.main {
    .gee-col-base();
    width: 760px;
}

.sidebar {
    .gee-col-base();
    width: 200px;
}
```

### Class-based (unsemantic) way

Define the pixel widths in your stylesheet.

```css
.container {
    width: 960px;
}

.main {
    width: 760px;
}

.sidebar {
    width: 200px;
}
```

Use the generic `.gee-col` class in your markup.

```html
<div class="gee-row container">
    <article class="gee-col main">...</article>
    <section class="gee-col sidebar">...</section>
</div>
```

Credits
-------

The grid system is based on [YUI's CSS Grids](http://yuilibrary.com/yui/docs/cssgrids/).

License
-------

Copyright (c) 2013 Jan Sorgalla.
Released under the [MIT](https://github.com/jsor/gee/blob/master/LICENSE) license.
