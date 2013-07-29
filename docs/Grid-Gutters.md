Grid Gutters
============

gee can be configured to have gutters between the units. Gutter widths must be
defined in percent.

Semantic way
------------

You can define a gutter by either changing the global variable `@gee-gutter` or
by passing the number as first argument to `.gee-grid()` and third argument to
the `.gee-unit()` mixin.

```css
@gee-gutter: 2%;

.container {
    .gee-grid();
}

.main {
    .gee-unit(9);
}

.sidebar {
    .gee-unit(3);
}

/** OR **/

.container {
    .gee-grid(2%);
}

.main {
    .gee-unit(9, 12, 2%);
}

.sidebar {
    .gee-unit(3, 12, 2%);
}
```

Class-based (unsemantic) way
----------------------------

Simply pass the gutter width as second argument to the `.gee-generate()` mixin.

```css
.gee-generate(12, 2%);
```
