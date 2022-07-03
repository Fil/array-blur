_This module is now obsolete, superseded by [d3.blur](https://github.com/d3/d3-array)_

# array-blur

_This code was excerpted from [d3-contour](https://github.com/d3/d3-contour), enriched and optimized. It now exists as a [pull-request](https://github.com/d3/d3-array/pull/151) to d3-array. It can be used as a plugin for [D3](https://d3js.org/) or as a stand-alone module._

To use call:
```js
<script src="https://unpkg.com/array-blur"></script>
```

or in node:
```js
const B = require("array-blur");
const blurred_data = B.blur().radius(1)([0, 0, 0, 13.5, 0, 0, 0]); // [0.5, 1.5, 3, 3.5, 3, 1.5, 0.5, width: 7, height: 1]
```



<a name="blur" href="#blur">#</a> <b>blur</b>() · [Source](https://github.com/fil/array-blur/blob/master/src/blur.js)

Creates a blur transformer, which can blur (or smooth) an *iterable* by three iterations of a moving average transform.

<a name="blur_radius" href="#blur_radius">#</a> *blur*.<b>radius</b>([*radius*])

If *radius* is specified, sets the radius of the transformation: on each iteration, the value of a point is transformed into the mean value of itself and the *radius* points of data surrounding it on the left and on the right (taking into account the edges). If *radius* is not specified, returns the current radius (if horizontal and vertical radii have been set separately, returns their average value). If *radius* is not an integer value, the blurring is applied partially. Defaults to 5.

<a name="blur_value" href="#blur_value">#</a> *blur*.<b>value</b>([*value*])

If *value* is specified, sets the *value* accessor, which will read the values of the *iterator*. If not specified, returns the current accessor. Defaults to the special *null* accessor, which copies the values directly (faster than an identity function).

Example:
```js
const blurred = blur().value(d => d.temperature)(data);
```

<a name="blur_width" href="#blur_width">#</a> *blur*.<b>width</b>([*width*])

If *width* is specified, sets the width of the transformation, otherwise returns the current width. When 0 < width < length, *blur* considers that the *array* describes values in two dimensions—as a rectangle of a certain width (height inferred as length divided by width). In that case each iteration involves an horizontal (x) blurring, followed by a vertical (y) blurring. Defaults to undefined (horizontal dimension).

<a name="blur_radiusX" href="#blur_radiusX">#</a> *blur*.<b>radiusX</b>([*radius*])

If *radius* is specified, sets the horizontal radius of the transformation, otherwise returns it. (Use 0 for vertical blurring.)

<a name="blur_radiusY" href="#blur_radiusY">#</a> *blur*.<b>radiusY</b>([*radius*])

If *radius* is specified, sets the vertical radius of the transformation, otherwise returns it. (Use 0 for horizontal blurring.)


