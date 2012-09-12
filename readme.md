# Golden Bootstrap
Golden Bootstrap is a bunch of less written css rules giving you the divine power of using golden ratio sized columns with Bootstrap.

## Getting started
Include golden-bootstrap.less in bootstrap.less, compile and that's it.

```
// Grid system and page structure
...
@import "golden-bootstrap/golden-bootstrap.less"; // Add support for Golden Bootstrap
```

## How it works
“Two quantities are in the golden ratio if the ratio of the sum of the quantities to the larger quantity is equal to the ratio of the larger quantity to the smaller one” (source). Under the hood it looks like this:

```
@goldenRatio:    1.6180339887498948482;
@goldenLarge:    1/@goldenRatio;
@goldenSmall:    1-@goldenLarge;
```

Golden Bootstrap uses @gridColumnWidth and @gridGutterWidth values specified in bootstrap's variables.less to generate the grid system.

## Fixed
Use Bootstrap's default fixed columns and nest a new .row with a set of .golden-small and .golden-large columns.

```html
<div class="row">
  <div class="span9">
    <div class="row">
      <div class="golden-small">...</div>
      <div class="golden-large">...</div>
    </div>
  </div>
</div>
```

Using Golden Bootstrap comes with a notable drawback: you can't nest any .span* in a .golden-small and .golden-large column.

### Fixed offsetting
Add .offset-golden-small or .offset-golden-large to a golden* column to offset it by it's counterpart.

```html
<div class="row">
  <div class="span9">
    <div class="row">
      <div class="golden-small offset-golden-large">...</div>
    </div>
  </div>
</div>
```

---

## Fluid
Keep your regular fluid grid scaffolding. To divide any .span* by the golden ratio, simply nest .golden-small and .golden-large under a .row-fluid.

```html
<div class="row-fluid">
  <div class="span12">
    <div class="row-fluid">
      <div class="golden-small">...</div>
      <div class="golden-large">...</div>
    </div>
  </div>
</div>
```

### Fluid nesting
You can nest any fluid column in .golden-small and .golden-large.

### Fluid offsetting
Use .offset-golden-small or .offset-golden-large to offset any golden* column by its counterpart.

---

## Forms
Apply Golden Bootstrap's grid to standard form controls through .controls for stacked behavior.

```html
<div class="controls">
  <input class="golden-small" type="text" placeholder=".golden-small">
  <input class="golden-large" type="text" placeholder=".golden-large">
</div><!-- /.controls -->
```

Use .controls-row for inline behavior.

```html
<div class="row">
  <div class="span9">
    <div class="controls controls-row">
      <input class="golden-small" type="text" placeholder=".golden-small">
      <input class="golden-large" type="text" placeholder=".golden-large">
    </div><!-- /.controls-row -->
  </div>
</div><!-- /.row -->
```

## Responsive
Like Bootstrap, you have to add another file to support responsive behaviors. To do so, simply include golden-bootstrap-responsive.less in responsive.less, compile and you're done.

```
// GOLDEN BOOTSTRAP RESPONSIVE
// ------------------ 
@import "golden-bootstrap/golden-bootstrap-responsive.less";
```

Golden Bootstrap uses @gridColumnWidth768, @gridGutterWidth768, @gridColumnWidth1200 and @gridGutterWidth1200 values specified in bootstrap's variables.less to adapt itself to mediaqueries.
