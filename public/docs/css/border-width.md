# border-width

The `border-width` [shorthand](shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the width of an element's border.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`border-bottom-width`](border-bottom-width)
- [`border-left-width`](border-left-width)
- [`border-right-width`](border-right-width)
- [`border-top-width`](border-top-width)

## Syntax

    /* Keyword values */
    border-width: thin;
    border-width: medium;
    border-width: thick;

    /* <length> values */ border-width: 4px;
    border-width: 1.2rem;

    /* vertical | horizontal */
    border-width: 2px 1.5em;

    /* top | horizontal | bottom */
    border-width: 1px 2em 1.5cm;

    /* top | right | bottom | left */
    border-width: 1px 2em 0 4rem;

    /* Global keywords */
    border-width: inherit;
    border-width: initial;
    border-width: unset;

The `border-width` property may be specified using one, two, three, or four values.

- When **one** value is specified, it applies the same width to **all four sides**.
- When **two** values are specified, the first width applies to the **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first width applies to the **top**, the second to the **left and right**, the third to the **bottom**.
- When **four** values are specified, the widths apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

### Values

`<line-width>`  
Defines the width of the border, either as an explicit nonnegative [`<length>`](length) or a keyword. If it's a keyword, it must be one of the following values:

<table><tbody><tr class="odd"><td><code>thin</code></td><td></td><td>A thin border</td></tr><tr class="even"><td><code>medium</code></td><td></td><td>A medium border</td></tr><tr class="odd"><td><code>thick</code></td><td></td><td>A thick border</td></tr></tbody></table>

**Note:** Because the specification doesn't define the exact thickness denoted by each keyword, the precise result when using one of them is implementation-specific. Nevertheless, they always follow the pattern `thin ≤ medium ≤ thick`, and the values are constant within a single document.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-width"><code>border-top-width</code></a>: <code>medium</code></li><li><a href="border-right-width"><code>border-right-width</code></a>: <code>medium</code></li><li><a href="border-bottom-width"><code>border-bottom-width</code></a>: <code>medium</code></li><li><a href="border-left-width"><code>border-left-width</code></a>: <code>medium</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-width"><code>border-bottom-width</code></a>: the absolute length or <code>0</code> if <a href="border-bottom-style"><code>border-bottom-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-left-width"><code>border-left-width</code></a>: the absolute length or <code>0</code> if <a href="border-left-style"><code>border-left-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-right-width"><code>border-right-width</code></a>: the absolute length or <code>0</code> if <a href="border-right-style"><code>border-right-style</code></a> is <code>none</code> or <code>hidden</code></li><li><a href="border-top-width"><code>border-top-width</code></a>: the absolute length or <code>0</code> if <a href="border-top-style"><code>border-top-style</code></a> is <code>none</code> or <code>hidden</code></li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-width"><code>border-bottom-width</code></a>: a <a href="length#interpolation">length</a></li><li><a href="border-left-width"><code>border-left-width</code></a>: a <a href="length#interpolation">length</a></li><li><a href="border-right-width"><code>border-right-width</code></a>: a <a href="length#interpolation">length</a></li><li><a href="border-top-width"><code>border-top-width</code></a>: a <a href="length#interpolation">length</a></li></ul></td></tr></tbody></table>

## Formal syntax

    <line-width>{1,4}where
    <line-width> = <length> | thin | medium | thick

## Examples

### A mix of values and lengths

#### HTML

    <p id="sval">
        one value: 6px wide border on all 4 sides</p>
    <p id="bival">
        two different values: 2px wide top and bottom border, 10px wide right and left border</p>
    <p id="treval">
        three different values: 0.3em top, 9px bottom, and zero width right and left</p>
    <p id="fourval">
        four different values: "thin" top, "medium" right, "thick" bottom, and 1em left</p>

#### CSS

    #sval {
      border: ridge #ccc;
      border-width: 6px;
    }
    #bival {
      border: solid red;
      border-width: 2px 10px;
    }
    #treval {
      border: dotted orange;
      border-width: 0.3em 0 9px;
    }
    #fourval {
      border: solid lightgreen;
      border-width: thin medium thick 1em;
    }
    p {
      width: auto;
      margin: 0.25em;
      padding: 0.25em;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-border-width">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-width' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No direct change; the <a href="length"><code>&lt;length&gt;</code></a> CSS data type extension has an effect on this property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#border-width-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border-width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the constraint that values' meaning must be constant inside a document.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#border-width">CSS Level 1<br />
<span class="small">The definition of 'border-width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`border-width`

1

12

1

4

3.5

1

2

18

4

10.1

3

1.0

## See also

- The border-related shorthand properties: [`border`](border), [`border-style`](border-style), [`border-color`](border-color)
- The border-width-related properties: [`border-bottom-width`](border-bottom-width), [`border-left-width`](border-left-width), [`border-right-width`](border-right-width), [`border-top-width`](border-top-width)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-width</a>
