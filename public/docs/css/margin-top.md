# margin-top

The `margin-top` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the [margin area](css_box_model/introduction_to_the_css_box_model) on the top of an element. A positive value places it farther from its neighbors, while a negative value places it closer.

This property has no effect on _non-[replaced](replaced_element)_ inline elements, such as [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) or [`<code>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code).

## Syntax

    /* <length> values */
    margin-top: 10px;  /* An absolute length */
    margin-top: 1em;   /* relative to the text size */
    margin-top: 5%;    /* relative to the nearest block container's width */

    /* Keyword values */
    margin-top: auto;

    /* Global values */
    margin-top: inherit;
    margin-top: initial;
    margin-top: unset;

The `margin-top` property is specified as the keyword `auto`, or a `<length>`, or a `<percentage>`. Its value can be positive, zero, or negative.

### Values

[`<length>`](length)  
The size of the margin as a fixed value.

[`<percentage>`](percentage)  
The size of the margin as a percentage, relative to the _width_ of the containing block.

`auto`  
The browser selects a suitable value to use. See [`margin`](margin).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, except elements with table <a href="display"><code>display</code></a> types other than <code>table-caption</code>, <code>table</code> and <code>inline-table</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>the percentage as specified or the absolute length</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <length> | <percentage> | auto

## Examples

### Setting positive and negative top margins

    .content { margin-top:   5%; }
    .sidebox { margin-top: 10px; }
    .logo    { margin-top: -5px; }
    #footer  { margin-top:  1em; }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-box-3/#propdef-margin-top">CSS Basic Box Model<br />
<span class="small">The definition of 'margin-top' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#margin-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'margin-top' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Removes its effect on inline elements.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#margin-top">CSS Level 1<br />
<span class="small">The definition of 'margin-top' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`margin-top`

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

- [`margin-right`](margin-right), [`margin-bottom`](margin-bottom), and [`margin-left`](margin-left) and the [`margin`](margin) shorthand
- The mapped logical properties: [`margin-block-start`](margin-block-start), [`margin-block-end`](margin-block-end), [`margin-inline-start`](margin-inline-start), and [`margin-inline-end`](margin-inline-end) and the shorthands [`margin-block`](margin-block) and [`margin-inline`](margin-inline)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top</a>
