# margin-left

The `margin-left` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the [margin area](css_box_model/introduction_to_the_css_box_model) on the left side of an element. A positive value places it farther from its neighbors, while a negative value places it closer.

The vertical margins of two adjacent boxes may fuse. This is called [_margin collapsing_](css_box_model/mastering_margin_collapsing).

In the rare cases where width is overconstrained (i.e., when all of `width`, `margin-left`, `border`, `padding`, the content area, and `margin-right` are defined), `margin-left` is ignored, and will have the same calculated value as if the `auto` value was specified.

## Syntax

    /* <length> values */
    margin-left: 10px;  /* An absolute length */
    margin-left: 1em;   /* relative to the text size */
    margin-left: 5%;    /* relative to the nearest block container's width */

    /* Keyword values */
    margin-left: auto;

    /* Global values */
    margin-left: inherit;
    margin-left: initial;
    margin-left: unset;

The `margin-left` property is specified as the keyword `auto`, or a `<length>`, or a `<percentage>`. Its value can be positive, zero, or negative.

### Values

[`<length>`](length)  
The size of the margin as a fixed value.

[`<percentage>`](percentage)  
The size of the margin as a percentage, relative to the _width_ of the containing block.

`auto`  
The left margin receives a share of the unused horizontal space, as determined mainly by the layout mode that is used. If the values of `margin-left` and `margin-right` are both `auto`, the calculated space is evenly distributed. This table summarizes the different cases:

<table><thead><tr class="header"><th>Value of <a href="display"><code>display</code></a></th><th>Value of <a href="float"><code>float</code></a></th><th>Value of <a href="position"><code>position</code></a></th><th>Computed value of <code>auto</code></th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><code>inline</code>, <code>inline-block</code>, <code>inline-table</code></td><td><em>any</em></td><td><code>static</code> or <code>relative</code></td><td><code>0</code></td><td>Inline layout mode</td></tr><tr class="even"><td><code>block</code>, <code>inline</code>, <code>inline-block</code>, <code>block</code>, <code>table</code>, <code>inline-table</code>, <code>list-item</code>, <code>table-caption</code></td><td><em>any</em></td><td><code>static</code> or <code>relative</code></td><td><code>0</code>, except if both <code>margin-left</code> and <code>margin-right</code> are set to <code>auto</code>. In this case, it is set to the value centering the element inside its parent.</td><td>Block layout mode</td></tr><tr class="odd"><td><code>block</code>, <code>inline</code>, <code>inline-block</code>, <code>block</code>, <code>table</code>, <code>inline-table</code>, <code>list-item</code>, <code>table-caption</code></td><td><code>left</code> or <code>right</code></td><td><code>static</code> or <code>relative</code></td><td><code>0</code></td><td>Block layout mode (floating element)</td></tr><tr class="even"><td><em>any</em> <code>table-*</code><em>, except</em> <code>table-caption</code></td><td><em>any</em></td><td><em>any</em></td><td><code>0</code></td><td>Internal <code>table-*</code> elements don't have margins, use <a href="border-spacing"><code>border-spacing</code></a> instead</td></tr><tr class="odd"><td><em>any, except <code>flex</code>,</em> <code>inline-flex</code><em>, or</em> <code>table-*</code></td><td><em>any</em></td><td><em><code>fixed</code></em> or <code>absolute</code></td><td><code>0</code>, except if both <code>margin-left</code> and <code>margin-right</code> are set to <code>auto</code>. In this case, it is set to the value centering the border area inside the available <code>width</code>, if fixed.</td><td>Absolutely positioned layout mode</td></tr><tr class="even"><td><code>flex</code>, <code>inline-flex</code></td><td><em>any</em></td><td><em>any</em></td><td><code>0</code>, except if there is any positive horizontal free space. In this case, it is evenly distributed to all horizontal <code>auto</code> margins.</td><td>Flexbox layout mode</td></tr></tbody></table>

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, except elements with table <a href="display"><code>display</code></a> types other than <code>table-caption</code>, <code>table</code> and <code>inline-table</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>the percentage as specified or the absolute length</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <length> | <percentage> | auto

## Examples

### Setting left margin using pixels and percentages

    .content { margin-left: 5%; }
    .sidebox { margin-left: 10px; }
    .logo    { margin-left: -5px; }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-box-3/#propdef-margin-left">CSS Basic Box Model<br />
<span class="small">The definition of 'margin-left' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant change from CSS 2.1.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-flexbox-1/#item-margins">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'margin-left' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines the behavior of <code>margin-left</code> on flex items.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/box.html#margin-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'margin-left' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Like in CSS1, but removes its effect on inline elements.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#margin-left">CSS Level 1<br />
<span class="small">The definition of 'margin-left' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`margin-left`

1

12

1

3

3.5

1

1

18

4

10.1

1

1.0

`auto`

1

12

The `auto` value is not supported in quirks mode.

1

6

The `auto` value is not supported in quirks mode.

3.5

1

37

18

4

14

1

1.0

## See also

- [`margin-top`](margin-top), [`margin-right`](margin-right), and [`margin-bottom`](margin-bottom) and the [`margin`](margin) shorthand
- The mapped logical properties: [`margin-block-start`](margin-block-start), [`margin-block-end`](margin-block-end), [`margin-inline-start`](margin-inline-start), and [`margin-inline-end`](margin-inline-end) and the shorthands [`margin-block`](margin-block) and [`margin-inline`](margin-inline)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left</a>
