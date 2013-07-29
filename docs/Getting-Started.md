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

We can now apply the grid behavior to the elements by using the `.gee-grid()`
and `.gee-unit()` mixins.

```css
.container {
    .gee-grid();
}

.main {
    .gee-unit(9);
}

.sidebar {
    .gee-unit(3);
}
```

By default, gee uses a 12-column grid. You can adjust the number of columns by
either changing the global variable `@gee-columns` or by passing the number as
second argument to the `.gee-unit()` mixin.

```css
@gee-columns: 24;

.main {
    .gee-unit(18);
}

.sidebar {
    .gee-unit(6);
}

/** OR **/

.main {
    .gee-unit(18, 24);
}

.sidebar {
    .gee-unit(6, 24);
}
```

Class-based (unsemantic) way
----------------------------

If you prefer a more traditional approach by using classes in your markup, you
can use the `.gee-generate()` mixin to generate all required classes in your
LESS stylesheet.

The arguments for the mixin are:

1. The number of columns (default is 12)
2. The gutter between the units in % (default is 0)
3. The prefix for the generated classes (default is gee- which results in
   class names like gee-grid, gee-unit-12, gee-unit-11 etc).

```css
.gee-generate(12, 0, gee-);
```

Here's the full list of generated classes you can use.

```css
.gee-grid {}
.gee-unit-12 {}
.gee-unit-11 {}
.gee-unit-10 {}
.gee-unit-9 {}
.gee-unit-8 {}
.gee-unit-7 {}
.gee-unit-6 {}
.gee-unit-5 {}
.gee-unit-4 {}
.gee-unit-3 {}
.gee-unit-2 {}
.gee-unit-1 {}
```

You can now use these classes in your HTML to apply the grid behavior.

```html
<div class="gee-grid container">
    <article class="gee-unit-9 main">...</article>
    <section class="gee-unit-3 sidebar">...</section>
</div>
```
