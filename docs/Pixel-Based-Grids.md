Pixel-Based Grids
=================

Sometimes you may have the requirement to use pixel-based unit widths.
Custom unit sizes can be applied by combining your custom widths with a
generic unit.

Semantic way
------------

Just use the `.gee-unit-base()` mixin.

```css
.container {
    .gee-grid();
    width: 960px;
}

.main {
    .gee-unit-base();
    width: 760px;
}

.sidebar {
    .gee-unit-base();
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

Use the generic `.gee-unit` class in your markup.

```html
<div class="gee-grid container">
    <article class="gee-unit main">...</article>
    <section class="gee-unit sidebar">...</section>
</div>
```
