Grid Gutters
============

gee can be configured to have gutters between the columns. Gutter widths must be
defined in percent.

Semantic way
------------

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

Class-based (unsemantic) way
----------------------------

Simply pass the gutter width as second argument to the `.gee-generate()` mixin.

```css
.gee-generate(12, 2%);
```
