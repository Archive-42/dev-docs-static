# border-radius

The `border-radius` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property rounds the corners of an element's outer border edge. You can set a single radius to make circular corners, or two radii to make elliptical corners.

The radius applies to the whole [`background`](background), even if the element has no border; the exact position of the clipping is defined by the [`background-clip`](background-clip) property.

The `border-radius` property does not apply to table elements when [`border-collapse`](border-collapse) is `collapse`.

**Note:** As with any shorthand property, individual sub-properties cannot inherit, such as in `border-radius:0 0 inherit inherit`, which would partially override existing definitions. Instead, the individual longhand properties have to be used.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`border-top-left-radius`](border-top-left-radius)
- [`border-top-right-radius`](border-top-right-radius)
- [`border-bottom-right-radius`](border-bottom-right-radius)
- [`border-bottom-left-radius`](border-bottom-left-radius)

## Syntax

    /* The syntax of the first radius allows one to four values */
    /* Radius is set for all 4 sides */
    border-radius: 10px;

    /* top-left-and-bottom-right | top-right-and-bottom-left */
    border-radius: 10px 5%;

    /* top-left | top-right-and-bottom-left | bottom-right */
    border-radius: 2px 4px 2px;

    /* top-left | top-right | bottom-right | bottom-left */
    border-radius: 1px 0 3px 4px;

    /* The syntax of the second radius allows one to four values */
    /* (first radius values) / radius */
    border-radius: 10px / 20px;

    /* (first radius values) / top-left-and-bottom-right | top-right-and-bottom-left */
    border-radius: 10px 5% / 20px 30px;

    /* (first radius values) / top-left | top-right-and-bottom-left | bottom-right */
    border-radius: 10px 5px 2em / 20px 25px 30%;

    /* (first radius values) / top-left | top-right | bottom-right | bottom-left */
    border-radius: 10px 5% / 20px 25em 30px 35em;

    /* Global values */
    border-radius: inherit;
    border-radius: initial;
    border-radius: unset;

The `border-radius` property is specified as:

- one, two, three, or four [`<length>`](length) or [`<percentage>`](percentage) values. This is used to set a single radius for the corners.
- followed optionally by "/" and one, two, three, or four `<length>` or `<percentage>` values. This is used to set an additional radius, so you can have elliptical corners.

### Values

<table><tbody><tr class="odd"><td><em>radius</em></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEUAAAA8BAMAAADCjmoTAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAhUExURf///8/n5gAAAICAgNDo5uzs7MHZ11RUVF5eXmlpafb29s+R8iEAAAB1SURBVEjHY2BQAgMGLAAhA2EZYwHoagSxALgaLkJqFBgYWIlToyiIEwgpqY+qIaiGi4AaUDgzMAviAyIGDKNqRtWMqhlJavCXLWJElM+jaohUg6seFILVgwzEq8FWdxuhqcHWBmCCq9HoAIImrGpmggBx5gAAEuWZYELeiroAAAAASUVORK5CYII=" alt="all-corner.png" class="default internal" width="69" height="60" /></td><td>Is a <a href="length"><code>&lt;length&gt;</code></a> or a <a href="percentage"><code>&lt;percentage&gt;</code></a> denoting a radius to use for the border in each corner of the border. It is used only in the one-value syntax.</td></tr><tr class="even"><td><em>top-left-and-bottom-right</em></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEUAAAA7BAMAAADfi1qrAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAVUExURc/n5v///wAAAICAgOzs7MHZ12lpacrarFUAAABYSURBVEjHYxBUAgNB3ECAAarGGBcwRKhhwAVAakSop0aBAQ8YVUNYjSAxaoQZGEbVjKoZVTOqhjg1rEpKiqNqaKyGCVxDEq0GZ7VtBFeDGwgRoyYNBBQFAEjjNtOWq4EXAAAAAElFTkSuQmCC" alt="top-left-bottom-right.png" class="default internal" width="69" height="59" /></td><td>Is a <a href="length"><code>&lt;length&gt;</code></a> or a <a href="percentage"><code>&lt;percentage&gt;</code></a> denoting a radius to use for the border in the top-left and bottom-right corners of the element's box. It is used only in the two-value syntax.</td></tr><tr class="odd"><td><em>top-right-and-bottom-left</em></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEUAAAA7BAMAAADfi1qrAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAYUExURf///8/n5gAAAICAgNDo5uzs7GlpaVRUVGEThy4AAABVSURBVEjHY2DADZTAAMRiNsYFkNQI4gLEq1GgWA0QCCmpj6qhWA3hcBYUMWAYVTOqZlTNSFLDqqSkOKqGLmpAAH98Ea8GZwVugFrT4wZqaUCQhE8FADxjjJR5xFuQAAAAAElFTkSuQmCC" alt="top-right-bottom-left.png" class="default internal" width="69" height="59" /></td><td>Is a <a href="length"><code>&lt;length&gt;</code></a> or a <a href="percentage"><code>&lt;percentage&gt;</code></a> denoting a radius to use for the border in the top-right and bottom-left corners of the element's box. It is used only in the two- and three-value syntaxes.</td></tr><tr class="even"><td><em>top-left</em></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEEAAAA5BAMAAACbqFvaAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAASUExURf///8/n5oCAgAAAANLp5+zs7OtBa1wAAAA/SURBVDjLY2AwBgMGPACiQgkXUICpEMQBRBQYWKmjwlAQNxhVgaGCgbAKJkHBURWjKkZVjKoYVUEfFUp4gQIAIzeEnWkMj6cAAAAASUVORK5CYII=" alt="top-left.png" class="default internal" width="65" height="57" /></td><td>Is a <a href="length"><code>&lt;length&gt;</code></a> or a <a href="percentage"><code>&lt;percentage&gt;</code></a> denoting a radius to use for the border in the top-left corner of the element's box. It is used only in the three- and four-value syntaxes.</td></tr><tr class="odd"><td><em>top-right</em></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEEAAAA5BAMAAACbqFvaAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAASUExURc/n5oCAgP///wAAAN3u7b/W1Y8X38EAAAA+SURBVDjLY1DCBZSNQcBIgUEQFxCGqRBgwAGY6aICCFhHVZCogoGwCgZHpVEVoypGVYyqGFVBLRWC+IGSAgCa/y3Z6Z7RTgAAAABJRU5ErkJggg==" alt="top-right.png" class="default internal" width="65" height="57" /></td><td>Is a <a href="length"><code>&lt;length&gt;</code></a> or a <a href="percentage"><code>&lt;percentage&gt;</code></a> denoting a radius to use for the border in the top-right corner of the element's box. It is used only in the four-value syntax.</td></tr><tr class="even"><td><em>bottom-right</em></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEIAAAA6BAMAAAD2C5J3AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAnUExURc/n5oCAgP///wAAANzu7ISSksng3h8fH56xr3+Ojerq6sPDw2JiYkZQ+8AAAABGSURBVDjLYxDED5SUGAQY8AHHURWjKkZVjKoYVTFYVAQbG4+qIF5FWlraZLwqOIzBgBgVOOtRGbCCYiUGJVxAm6AKLagtAAxCNXheC0PNAAAAAElFTkSuQmCC" alt="bottom-rigth.png" class="default internal" width="66" height="58" /></td><td>Is a <a href="length"><code>&lt;length&gt;</code></a> or a <a href="percentage"><code>&lt;percentage&gt;</code></a> denoting a radius to use for the border in the bottom-right corner of the element's box. It is used only in the three- and four-value syntaxes.</td></tr><tr class="odd"><td><em>bottom-left</em></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEEAAAA6BAMAAAAdPCl0AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAASUExURc/n5oCAgP///wAAANLp5+zs7LeKl/gAAAA8SURBVDjLY1BSFMQLBBiUFBnwAZZRFaMqRlWMqhhVQT8VqsbGBqMqqK4CBPDFC7Eq8NWmEBVKuIACYRUAjRAoGhOrWNMAAAAASUVORK5CYII=" alt="bottom-left.png" class="default internal" width="65" height="58" /></td><td>Is a <a href="length"><code>&lt;length&gt;</code></a> or a <a href="percentage"><code>&lt;percentage&gt;</code></a> denoting a radius to use for the border in the bottom-left corner of the element's box. It is used only in the four-value syntax.</td></tr></tbody></table>

[`<length>`](length)  
Denotes the size of the circle radius, or the semi-major and semi-minor axes of the ellipse, using length values. Negative values are invalid.

[`<percentage>`](percentage)  
Denotes the size of the circle radius, or the semi-major and semi-minor axes of the ellipse, using percentage values. Percentages for the horizontal axis refer to the width of the box; percentages for the vertical axis refer to the height of the box. Negative values are invalid.

For example:

    border-radius: 1em/5em;

    /* ... is equivalent to: */
    border-top-left-radius:     1em 5em;
    border-top-right-radius:    1em 5em;
    border-bottom-right-radius: 1em 5em;
    border-bottom-left-radius:  1em 5em;

    border-radius: 4px 3px 6px / 2px 4px;

    /* ... is equivalent to: */
    border-top-left-radius:     4px 2px;
    border-top-right-radius:    3px 4px;
    border-bottom-right-radius: 6px 2px;
    border-bottom-left-radius:  3px 4px;

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-left-radius"><code>border-top-left-radius</code></a>: <code>0</code></li><li><a href="border-top-right-radius"><code>border-top-right-radius</code></a>: <code>0</code></li><li><a href="border-bottom-right-radius"><code>border-bottom-right-radius</code></a>: <code>0</code></li><li><a href="border-bottom-left-radius"><code>border-bottom-left-radius</code></a>: <code>0</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements; but User Agents are not required to apply to <code>table</code> and <code>inline-table</code> elements when <a href="border-collapse"><code>border-collapse</code></a> is <code>collapse</code>. The behavior on internal table elements is undefined for the moment.. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the corresponding dimension of the border box</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-left-radius"><code>border-bottom-left-radius</code></a>: two absolute <a href="length"><code>&lt;length&gt;</code></a>s or <a href="percentage"><code>&lt;percentage&gt;</code></a>s</li><li><a href="border-bottom-right-radius"><code>border-bottom-right-radius</code></a>: two absolute <a href="length"><code>&lt;length&gt;</code></a>s or <a href="percentage"><code>&lt;percentage&gt;</code></a>s</li><li><a href="border-top-left-radius"><code>border-top-left-radius</code></a>: two absolute <a href="length"><code>&lt;length&gt;</code></a>s or <a href="percentage"><code>&lt;percentage&gt;</code></a>s</li><li><a href="border-top-right-radius"><code>border-top-right-radius</code></a>: two absolute <a href="length"><code>&lt;length&gt;</code></a>s or <a href="percentage"><code>&lt;percentage&gt;</code></a>s</li></ul></td></tr><tr class="even"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-left-radius"><code>border-top-left-radius</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li><li><a href="border-top-right-radius"><code>border-top-right-radius</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li><li><a href="border-bottom-right-radius"><code>border-bottom-right-radius</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li><li><a href="border-bottom-left-radius"><code>border-bottom-left-radius</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li></ul></td></tr></tbody></table>

## Formal syntax

    <length-percentage>{1,4} [ / <length-percentage>{1,4} ]?where
    <length-percentage> = <length> | <percentage>

## Examples

      border: solid 10px;
      /* the border will curve into a 'D' */
      border-radius: 10px 40px 40px 10px;

      border: groove 1em red;
      border-radius: 2em;

      background: gold;
      border: ridge gold;
      border-radius: 13em/3em;

      border: none;
      border-radius: 40px 10px;

      border: none;
      border-radius: 50%;

      border: dotted;
      border-width: 10px 4px;
      border-radius: 10px 40px;

      border: dashed;
      border-width: 2px 4px;
      border-radius: 40px;

### Live Samples

- Sample 1 : <https://jsfiddle.net/Tripad/qnGKj/2/>
- Sample 2 : <https://jsfiddle.net/Tripad/qnGKj/3/>
- Sample 3 : <https://jsfiddle.net/Tripad/qnGKj/4/>
- Sample 4 : <https://jsfiddle.net/Tripad/qnGKj/5/>
- Sample 5 : <https://jsfiddle.net/Tripad/qnGKj/6/>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#border-radius">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-radius' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`border-radius`

4

Chrome ignores `border-radius` on `<select>` elements unless `-webkit-appearance` is overridden to an appropriate value.

1

12

12

4

\["Prior to Firefox 50, border styles of rounded corners (with `border-radius`) were always rendered as if `border-style` was `solid`. This has been fixed in Firefox 50.", "To conform to the CSS3 standard, Firefox 4 changes the handling of [`<percentage>`](https://developer.mozilla.org/docs/Web/CSS/percentage) values to match the specification. You can specify an ellipse as a border on an arbitrary sized element with `border-radius: 50%;`. Firefox 4 also makes rounded corners clip content and images if [`overflow`](https://developer.mozilla.org/docs/Web/CSS/overflow)`: visible` is not set."\]

1-12

9

10.5

Before Opera 11.60, replaced elements with `border-radius` do not have rounded corners.

5

Safari ignores `border-radius` on `<select>` elements unless `-webkit-appearance` is overridden to an appropriate value.

3

≤37

2

18

4

Prior to Firefox 50, border styles of rounded corners (with `border-radius`) were always rendered as if `border-style` was `solid`. This has been fixed in Firefox 50.

4-14

11

4.2

Safari ignores `border-radius` on `<select>` elements unless `-webkit-appearance` is overridden to an appropriate value.

1

1.0

`elliptical_borders`

1

Before Chrome 4, the slash `/` notation is unsupported. If two values are specified, then an elliptical border is drawn on all four corners. `-webkit-border-radius: 40px 10px;` is equivalent to `border-radius: 40px / 10px;`.

12

4

9

10.5

3

Before Safari 5, the slash `/` notation is unsupported. If two values are specified, then an elliptical border is drawn on all four corners. `-webkit-border-radius: 40px 10px;` is equivalent to `border-radius: 40px / 10px;`.

≤37

18

4

11

4.2

1.0

`percentages`

8

12

4

`<percentage>` values are implemented in a non-standard way prior to Firefox 4. Both horizontal and vertical radii were relative to the width of the border box.

9

11.5

The implementation of `<percentage>` values was buggy in Opera prior to 11.50.

5.1

≤37

18

4

11.5

6

1.0

`4_values_for_4_corners`

4

12

4

9

10.5

5

≤37

18

4

11

4.2

1.0

## See also

- Border-radius-related CSS properties: [`border-top-left-radius`](border-top-left-radius), [`border-top-right-radius`](border-top-right-radius), [`border-bottom-right-radius`](border-bottom-right-radius), [`border-bottom-left-radius`](border-bottom-left-radius)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius</a>
