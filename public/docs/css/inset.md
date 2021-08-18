# inset

The `inset` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is a shorthand that corresponds to the [`top`](top), [`right`](right), [`bottom`](bottom), and/or [`left`](left) properties. It has the same multi-value syntax of the [`margin`](margin) shorthand.

While part of the _CSS Logical Properties_ specification, it does not define _logical_ offsets. It defines _physical_ offsets, regardless of the element's writing mode, directionality, and text orientation.

    /* <length> values */
    inset: 10px; /* value applied to all edges */
    inset: 4px 8px; /* top/bottom left/right */
    inset: 5px 15px 10px; /* top left/right bottom */
    inset: 2.4em 3em 3em 3em; /* top right bottom left */

    /* <percentage>s of the width (left/right) or height (top/bottom) of the containing block */
    inset: 10% 5% 5% 5%;

    /* Keyword value */
    inset: auto;

    /* Global values */
    inset: inherit;
    inset: initial;
    inset: unset;

## Syntax

### Values

The `inset` property takes the same values as the [`left`](left) property.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>positioned elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>relative to the containing block’s size in the corresponding axis (e.g. width for left or right, height for top or bottom)</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>same as box offsets: <a href="top"><code>top</code></a>, <a href="right"><code>right</code></a>, <a href="bottom"><code>bottom</code></a>, <a href="left"><code>left</code></a> properties except that directions are logical</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <'top'>{1,4}

## Examples

### Setting offsets for an element

#### HTML

    <div>
      <span class="exampleText">Example text</span>
    </div>

#### CSS

    div {
      background-color: yellow;
      width: 150px;
      height: 120px;
      position: relative;
    }

    .exampleText {
      writing-mode: sideways-rl;
      position: absolute;
      inset: 20px 40px 30px 10px;
      background-color: #c8c800;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-inset">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'inset' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`inset`

87

69

79

66

No

73

56

14.1

87

87

69

66

48

14.5

No

## See also

- The longhand box offset properties: [`top`](top), [`right`](right), [`bottom`](bottom), and [`left`](left).
- The mapped logical shorthands: [`inset-block`](inset-block) and [`inset-inline`](inset-inline)
- The [`margin`](margin) shorthand multi-value syntax.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/inset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/inset</a>
