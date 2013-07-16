Getting Started
===============

Download [gee.less](https://raw.github.com/jsor/gee/master/gee.less) and import
it into your LESS stylesheet:

```css
@import 'gee.less';
```

Semantic way
------------

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

Class-based (unsemantic) way
----------------------------

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
