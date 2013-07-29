Responsive Grids
================

Responsive grids can be simply archieved by adding a little extra code.

Semantic way
------------

You can change the width of units based on media queries by using the
`.gee-unit-width()` mixin.

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

@media (max-width: 767px) {
    .main,
    .sidebar {
        .gee-unit-width(12);
    }
}
```

Class-based (unsemantic) way
----------------------------

Add the following code to your stylesheet to collapse units to full width on
screens lower than 768px.

```css
@media (max-width: 767px) {
    .gee-grid > [class*="gee-unit"] {
        width: 100%;
    }
}
```
