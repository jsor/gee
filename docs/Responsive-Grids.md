Responsive Grids
================

Responsive grids can be simply archieved by adding a little extra code.

Semantic way
------------

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

Class-based (unsemantic) way
----------------------------

Add the following code to your stylesheet to collapse columns to full width on
screens lower than 768px.

```css
@media (max-width: 767px) {
    .gee-row > [class*="gee-col"] {
        width: 100%;
    }
}
```
