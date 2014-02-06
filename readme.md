# Golden Bootstrap
Golden Bootstrap is a tiny add-on for [Bootstrap](http://getbootstrap.com/) giving you the [divine](http://en.wikipedia.org/wiki/Sacred_geometry) power of using golden ratio sized columns. Available both for [Less](http://lesscss.org/) and [Sass](http://sass-lang.com/) CSS preprocessors.

## Usage
Include `golden-bootstrap.less` in `bootstrap.less` or `golden-bootstrap.scss` in `bootstrap.scss`, and that's it.

```sass
// Core CSS
//...
@import "golden-bootstrap/golden-bootstrap.scss"; // Add support for Golden Bootstrap
```
Then, like you would do with any other Bootstrap default column, simply use a set of `.golden-sm` and `.golden-lg` columns:

```html
<div class="row">
  <div class="col-golden-sm">...</div>
  <div class="col-golden-lg">...</div>
</div>
```

```html
<div class="row">
  <div class="col-golden-offset-sm">...</div>
</div>

<div class="row">
  <div class="col-golden-offset-lg">...</div>
</div>

<form class="form-horizontal" role="form">
  <div class="form-group">
    <label class="col-golden-sm control-label">Email</label>
    <div class="col-golden-lg">
      <input type="email" class="form-control" placeholder="Email">
    </div>
  </div>
</form>
```

## How it works
“Two quantities are in the golden ratio if the ratio of the sum of the quantities to the larger quantity is equal to the ratio of the larger quantity to the smaller one” ([source](http://en.wikipedia.org/wiki/Golden_ratio)). Under the hood it looks like this:

```sass
$golden-ratio:    1.6180339887498948482;
$golden-lg:       (1 / $golden-ratio);
$golden-sm:       (1 - $golden-lg);
```

Golden Bootstrap uses `$grid-gutter-width` values specified in bootstrap's `variables.scss` to generate the grid system.


## Responsive



## Versionning

Golden Bootstrap follows the same versionning than Bootstrap, see [versionning](https://github.com/twbs/bootstrap?source=c#versioning).


---

# Author
[Philippe Dionne](http://phildionne.com)

# Copyright and license

Copyright 2014 Philippe Dionne

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this work except in compliance with the License. You may obtain a copy of the License in the LICENSE file, or at:

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
