Pixel-Based Grids
=================

Sometimes you may have the requirement to use pixel-based column widths.
Custom column sizes can be applied by combining your custom widths with a
generic column.

Semantic way
------------

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

Class-based (unsemantic) way
----------------------------

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
