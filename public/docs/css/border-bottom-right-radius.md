# border-bottom-right-radius

The `border-bottom-right-radius` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property rounds the bottom-right corner of an element by specifying the radius (or the radius of the semi-major and semi-minor axes) of the ellipse defining the curvature of the corner.

The rounding can be a circle or an ellipse, or if one of the value is `0` no rounding is done and the corner is square.

<img src="data:image/png;base64,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" alt="border-bottom-right-radius.png" class="default internal" width="597" height="164" />

A background, being an image or a color, is clipped at the border, even a rounded one; the exact location of the clipping is defined by the value of the [`background-clip`](background-clip) property.

**Note:** If the value of this property is not set in a [`border-radius`](border-radius) shorthand property that is applied to the element after the `border-bottom-right-radius` CSS property, the value of this property is then reset to its initial value by the [shorthand property](shorthand_properties).

## Syntax

    /* The corner is a circle */
    /* border-bottom-right-radius: radius */
    border-bottom-right-radius: 3px;

    /* Percentage values */
    border-bottom-right-radius: 20%; /* corner of a circle if box is a square or else corner of a rectangle */
    border-bottom-right-radius: 20% 20%; /* same as above */ /* 20% of horizontal(width) and vertical(height) */
    border-bottom-right-radius: 20% 10%; /* 20% of horizontal(width) and 10% of vertical(height) */

    /*The corner is an ellipse */
    /* border-bottom-right-radius: horizontal vertical */
    border-bottom-right-radius: 0.5em 1em;

    border-bottom-right-radius: inherit;

With one value:

- the value is a [`<length>`](length) or a [`<percentage>`](percentage) denoting the radius of the circle to use for the border in that corner.

With two values:

- the first value is a [`<length>`](length) or a [`<percentage>`](percentage) denoting the horizontal semi-major axis of the ellipse to use for the border in that corner.
- the second value is a [`<length>`](length) or a [`<percentage>`](percentage) denoting the vertical semi-major axis of the ellipse to use for the border in that corner.

### Values

`<length-percentage>`  
Denotes the size of the circle radius or the semi-major and semi-minor axes of the ellipse. As absolute length it can be expressed in any unit allowed by the CSS [`<length>`](length) data type. Percentages for the horizontal axis refer to the width of the box, percentages for the vertical axis refer to the height of the box. Negative values are invalid.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; but User Agents are not required to apply to <code>table</code> and <code>inline-table</code> elements when <a href="border-collapse"><code>border-collapse</code></a> is <code>collapse</code>. The behavior on internal table elements is undefined for the moment.. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the corresponding dimension of the border box</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>two absolute <a href="length"><code>&lt;length&gt;</code></a>s or <a href="percentage"><code>&lt;percentage&gt;</code></a>s</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <length-percentage>{1,2}where
    <length-percentage> = <length> | <percentage>

## Examples

### Examples of different border-bottom-right-radius values

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Live example</th><th>Code</th></tr></thead><tbody><tr class="odd"><td>.</td><td>An arc of circle is used as the border<pre data-language="css"><code>div {
  border-bottom-right-radius: 40px 40px;
}</code></pre></td></tr><tr class="even"><td>.</td><td>An arc of ellipse is used as the border<pre data-language="css"><code>div {
  border-bottom-right-radius: 40px 20px;
}</code></pre></td></tr><tr class="odd"><td>.</td><td>The box is a square: an arc of circle is used as the border<pre data-language="css"><code>div {
  border-bottom-right-radius: 40%;
}</code></pre></td></tr><tr class="even"><td>.</td><td>The box is not a square: an arc of ellipse is used as the border<pre data-language="css"><code>div {
  border-bottom-right-radius: 40%;
}</code></pre></td></tr><tr class="odd"><td>.</td><td>The background color is clipped at the border<pre data-language="css"><code>div {
  border-bottom-right-radius:40%;
  border-style: black 3px double;
  background-color: rgb(250,20,70);
  background-clip: content-box;
}</code></pre></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#propdef-border-bottom-right-radius">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-bottom-right-radius' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-bottom-right-radius`

4

1

12

12

4

Prior to Firefox 50, border styles of rounded corners were always rendered as if `border-style` was solid. This has been fixed in Firefox 50.

49

44

1-12

9

10.5

15

5

3

≤37

≤37

18

18

4

Prior to Firefox 50, border styles of rounded corners were always rendered as if `border-style` was solid. This has been fixed in Firefox 50.

49

44

4-14

11

14

4.2

1

1.0

1.0

`elliptical_corners`

1

12

3.5

9

10.5

3

≤37

18

4

14

1

1.0

`percentages`

4

12

4

1

Before Firefox 4, the [`<percentage>`](https://developer.mozilla.org/docs/Web/CSS/percentage) was relative to the width of the box even when specifying the radius for a height. This implied that `-moz-border-radius-bottomright` was always drawing an arc of circle, and never an ellipse, when followed by a single value.

9

10.5

5

≤37

18

4

14

4.2

1.0

## See also

- [`border-radius`](border-radius) shorthand property
- [`border-top-right-radius`](border-top-right-radius), [`border-bottom-left-radius`](border-bottom-left-radius), and [`border-top-left-radius`](border-top-left-radius)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-right-radius" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-right-radius</a>
