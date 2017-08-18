# Custom Properties Grid

A very simple, configurable, responsive grid with CSS custom properties & flexbox.

* * *

## Features

* Per row gutter sizes (default 20px)
* Per row column counts (default 12 columns)
* Column offsets (default no offset)
* Column spans (default span 1 column)

## CSS

The entire code needed for a working grid is below:

```css
@media screen and (min-width: 767px) {
    .row {
        --columns: 12;
        --gutter: 20px;
        display: flex;
        flex-wrap: wrap;
        margin: 0 calc(var(--gutter) * -.5);
    }
    .row > .column {
        --span: 1;
        --offset: 0;
        box-sizing: border-box;
        padding: 0 calc(var(--gutter) * .5);
        width: calc(100% / var(--columns) * var(--span));
        margin-left: calc(100% / var(--columns) * var(--offset));
    }
}
```

## Support

Modern browsers (excluding Edge) - [http://caniuse.com/#feat=css-variables](http://caniuse.com/#feat=css-variables)

## Examples

A full list of examples can be found on the [demo page](https://htmlpreview.github.io/?https://github.com/chrisgeary92/css-custom-properties-grid/blob/master/demo.html)

```html
<!-- 12 column grid.. 1|1|1|333|666666 -->
<div class="row">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column" style="--span: 3"></div>
    <div class="column" style="--span: 6"></div>
</div>
```

```html
<!-- 5 column grid, 5px gutters -->
<div class="row" style="--gutter: 5px; --columns: 5">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
</div>
```

```html
<!-- 5 column grid, first column offset by 1 -->
<div class="row" style="--columns: 5">
    <div class="column" style="--offset: 1"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
</div>
```

A full list of examples can be found on the [demo page](https://htmlpreview.github.io/?https://github.com/chrisgeary92/css-custom-properties-grid/blob/master/demo.html)
