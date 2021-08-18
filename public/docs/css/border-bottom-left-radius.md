# border-bottom-left-radius

The `border-bottom-left-radius` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property rounds the bottom-left corner of an element by specifying the radius (or the radius of the semi-major and semi-minor axes) of the ellipse defining the curvature of the corner.

The rounding can be a circle or an ellipse, or if one of the value is `0` no rounding is done and the corner is square.

<img src="data:image/png;base64,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" alt="border-bottom-left-radius.png" class="default internal" width="549" height="164" />

A background, being an image or a color, is clipped at the border, even a rounded one; the exact location of the clipping is defined by the value of the [`background-clip`](background-clip) property.

**Note:** If the value of this property is not set in a [`border-radius`](border-radius) shorthand property that is applied to the element after the `border-bottom-left-radius` CSS property, the value of this property is then reset to its initial value by the [shorthand property](shorthand_properties).

## Syntax

    /* the corner is a circle */
    /* border-bottom-left-radius: radius */
    border-bottom-left-radius: 3px;

    /* Percentage values */

    /* circle if box is a square or ellipse if box is a rectangle */
    border-bottom-left-radius: 20%;

    /* same as above: 20% of horizontal(width) and vertical(height) */
    border-bottom-left-radius: 20% 20%;

    /* 20% of horizontal(width) and 10% of vertical(height) */
    border-bottom-left-radius: 20% 10%;

    /* the corner is an ellipse */
    /* border-bottom-left-radius: horizontal vertical */
    border-bottom-left-radius: 0.5em 1em;

    border-bottom-left-radius: inherit;

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

### Examples of different border-bottom-left-radius values

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Live example</th><th>Code</th></tr></thead><tbody><tr class="odd"><td>.</td><td>An arc of circle is used as the border<pre data-language="css"><code>div {
  border-bottom-left-radius: 40px 40px;
}</code></pre></td></tr><tr class="even"><td>.</td><td>An arc of ellipse is used as the border<pre data-language="css"><code>div {
  border-bottom-left-radius: 40px 20px;
}</code></pre></td></tr><tr class="odd"><td>.</td><td>The box is a square: an arc of circle is used as the border<pre data-language="css"><code>div {
  border-bottom-left-radius: 40%;
}</code></pre></td></tr><tr class="even"><td>.</td><td>The box is not a square: an arc of ellipse is used as the border<pre data-language="css"><code>div {
  border-bottom-left-radius: 40%;
}</code></pre></td></tr><tr class="odd"><td>.</td><td>The background color is clipped at the border<pre data-language="css"><code>div {
  border-bottom-left-radius:40%;
  border-style: black 3px double;
  background-color: rgb(250,20,70);
  background-clip: content-box;
}</code></pre></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#propdef-border-bottom-left-radius">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-bottom-left-radius' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-bottom-left-radius`

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

Before Firefox 4, the [`<percentage>`](https://developer.mozilla.org/docs/Web/CSS/percentage) was relative to the width of the box even when specifying the radius for a height. This implied that `-moz-border-radius-bottomleft` was always drawing an arc of circle, and never an ellipse, when followed by a single value.

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
- [`border-top-right-radius`](border-top-right-radius), [`border-bottom-right-radius`](border-bottom-right-radius), and [`border-top-left-radius`](border-top-left-radius)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-left-radius" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-left-radius</a>
