# border-top-right-radius

The `border-top-right-radius` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property rounds the top-right corner of an element by specifying the radius (or the radius of the semi-major and semi-minor axes) of the ellipse defining the curvature of the corner.

The rounding can be a circle or an ellipse, or if one of the value is `0` no rounding is done and the corner is square.

<img src="data:image/png;base64,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" alt="border-top-right-radius.png" class="default internal" width="549" height="164" />

A background, being an image or a color, is clipped at the border, even a rounded one; the exact location of the clipping is defined by the value of the [`background-clip`](background-clip) property.

**Note:** If the value of this property is not set in a [`border-radius`](border-radius) shorthand property that is applied to the element after the `border-top-right-radius` CSS property, the value of this property is then reset to its initial value by the [shorthand property](shorthand_properties).

## Syntax

    /* the corner is a circle */
    /* border-top-right-radius: radius */
    border-top-right-radius: 3px;

    /* the corner is an ellipse */
    /* border-top-right-radius: horizontal vertical */
    border-top-right-radius: 0.5em 1em;

    border-top-right-radius: inherit;

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

### Examples of different border-top-right-radius values

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Live example</th><th>Code</th></tr></thead><tbody><tr class="odd"><td></td><td>An arc of circle is used as the border<pre data-language="css"><code>div {
  border-top-right-radius: 40px 40px;
}</code></pre></td></tr><tr class="even"><td></td><td>An arc of ellipse is used as the border<pre data-language="css"><code>div {
  border-top-right-radius: 40px 20px;
}</code></pre></td></tr><tr class="odd"><td></td><td>The box is a square: an arc of circle is used as the border<pre data-language="css"><code>div {
  border-top-right-radius: 40%;
}</code></pre></td></tr><tr class="even"><td>.</td><td>The box is not a square: an arc of ellipse is used as the border<pre data-language="css"><code>div {
  border-top-right-radius: 40%;
}</code></pre></td></tr><tr class="odd"><td></td><td>The background color is clipped at the border<pre data-language="css"><code>div {
  border-top-right-radius:40%;
  border-style: black 3px double;
  background-color: rgb(250,20,70);
  background-clip: content-box;
}</code></pre></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-border-radius">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-top-right-radius' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-top-right-radius`

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

Before Firefox 4, the [`<percentage>`](https://developer.mozilla.org/docs/Web/CSS/percentage) was relative to the width of the box even when specifying the radius for a height. This implied that `-moz-border-radius-topright` was always drawing an arc of circle, and never an ellipse, when followed by a single value.

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
- [`border-bottom-right-radius`](border-bottom-right-radius), [`border-bottom-left-radius`](border-bottom-left-radius), and [`border-top-left-radius`](border-top-left-radius)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-right-radius" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-right-radius</a>
