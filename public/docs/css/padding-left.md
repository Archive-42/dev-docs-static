# padding-left

The `padding-left` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the width of the [padding area](css_box_model/introduction_to_the_css_box_model#padding-area) to the left of an element.

An element's padding area is the space between its content and its border.

**Note:** The [`padding`](padding) property can be used to set paddings on all four sides of an element with a single declaration.

## Syntax

    /* <length> values */
    padding-left: 0.5em;
    padding-left: 0;
    padding-left: 2cm;

    /* <percentage> value */
    padding-left: 10%;

    /* Global values */
    padding-left: inherit;
    padding-left: initial;
    padding-left: unset;

The `padding-left` property is specified as a single value chosen from the list below. Unlike margins, negative values are not allowed for padding.

### Values

[`<length>`](length)  
The size of the padding as a fixed value. Must be nonnegative.

[`<percentage>`](percentage)  
The size of the padding as a percentage, relative to the _width_ of the containing block. Must be nonnegative.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, except <code>table-row-group</code>, <code>table-header-group</code>, <code>table-footer-group</code>, <code>table-row</code>, <code>table-column-group</code> and <code>table-column</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>the percentage as specified or the absolute length</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <length> | <percentage>

## Examples

### Setting left padding using pixels and percentages

    .content { padding-left: 5%; }
    .sidebox { padding-left: 10px; }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-box-3/#propdef-padding-left">CSS Basic Box Model<br />
<span class="small">The definition of 'padding-left' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#padding-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'padding-left' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#padding-left">CSS Level 1<br />
<span class="small">The definition of 'padding-left' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`padding-left`

1

12

1

4

3.5

1

≤37

18

4

14

1

1.0

## See also

- [Introduction to the CSS basic box model](css_box_model/introduction_to_the_css_box_model)
- [`padding-top`](padding-top), [`padding-right`](padding-right), [`padding-bottom`](padding-bottom) and the [`padding`](padding) shorthand
- The mapped logical properties: [`padding-block-start`](padding-block-start), [`padding-block-end`](padding-block-end), [`padding-inline-start`](padding-inline-start), and [`padding-inline-end`](padding-inline-end) and the shorthands [`padding-block`](padding-block) and [`padding-inline`](padding-inline)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding-left" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/padding-left</a>
