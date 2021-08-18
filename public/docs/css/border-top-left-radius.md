# border-top-left-radius

The `border-top-left-radius` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property rounds the top-left corner of an element by specifying the radius (or the radius of the semi-major and semi-minor axes) of the ellipse defining the curvature of the corner.

The rounding can be a circle or an ellipse, or if one of the value is `0,`no rounding is done and the corner is square.

<img src="data:image/png;base64,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" alt="border-radius.png" class="default internal" width="549" height="164" />

A background, being an image or a color, is clipped at the border, even a rounded one; the exact location of the clipping is defined by the value of the [`background-clip`](background-clip) property.

**Note:** If the value of this property is not set in a [`border-radius`](border-radius) shorthand property that is applied to the element after the `border-top-left-radius` CSS property, the value of this property is then reset to its initial value by the [shorthand property](shorthand_properties).

## Syntax

    /* the corner is a circle */
    /* border-top-left-radius: radius */
    border-top-left-radius: 3px;

    /* the corner is an ellipse */
    /* border-top-left-radius: horizontal vertical */
    border-top-left-radius: 0.5em 1em;

    border-top-left-radius: inherit;

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

### Examples of different border-top-left-radius values

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Live example</th><th>Code</th></tr></thead><tbody><tr class="odd"><td></td><td>An arc of ellipse is used as the border<pre data-language="css"><code>div {
  border-top-left-radius: 40px 40px;
}</code></pre></td></tr><tr class="even"><td></td><td>An arc of ellipse is used as the border<pre data-language="css"><code>div {
  border-top-left-radius: 40px 20px;
}</code></pre></td></tr><tr class="odd"><td></td><td>The box is a square: an arc of circle is used as the border<pre data-language="css"><code>div {
  border-top-left-radius: 40%;
}</code></pre></td></tr><tr class="even"><td></td><td>The box is not a square: an arc of ellipse is used as the border<pre data-language="css"><code>div {
  border-top-left-radius: 40%;
}</code></pre></td></tr><tr class="odd"><td></td><td>The background color is clipped at the border<pre data-language="css"><code>div {
  border-top-left-radius:40%;
  border: 3px double black;
  background-color: rgb(250,20,70);
  background-clip: content-box;
}</code></pre></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-border-radius">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-top-left-radius' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-top-left-radius`

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

Before Firefox 4, the [`<percentage>`](https://developer.mozilla.org/docs/Web/CSS/percentage) was relative to the width of the box even when specifying the radius for a height. This implied that `-moz-border-radius-topleft` was always drawing an arc of circle, and never an ellipse, when followed by a single value.

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
- [`border-top-right-radius`](border-top-right-radius), [`border-bottom-right-radius`](border-bottom-right-radius), and [`border-bottom-left-radius`](border-bottom-left-radius)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-left-radius" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-left-radius</a>
