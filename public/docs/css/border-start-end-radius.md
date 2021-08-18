# border-start-end-radius

The `border-start-end-radius` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines a logical border radius on an element, which maps to a physical border radius depending on the element's [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation). This is useful when building styles to work regardless of the [text orientation](text-orientation) and [writing mode](css_writing_modes).

    /* <length> values */
    /* With one value the corner will be a circle */
    border-start-end-radius: 10px;
    border-start-end-radius: 1em;

    /* With two values the corner will be an ellipse */
    border-start-end-radius: 1em 2em;

    /* Global values */
    border-start-end-radius: inherit;
    border-start-end-radius: initial;
    border-start-end-radius: unset;

This property affects the corner between the block-start and the inline-end sides of the element. For instance, in a `horizontal-tb` writing mode with `ltr` direction, it corresponds to the [`border-top-right-radius`](border-top-right-radius) property.

## Syntax

### Values

`<length-percentage>`  
Denotes the size of the circle radius or the semi-major and semi-minor axes of the ellipse. As absolute length it can be expressed in any unit allowed by the CSS [`<length>`](length) data type. Percentages for the horizontal axis refer to the width of the box, percentages for the vertical axis refer to the height of the box. Negative values are invalid.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; but User Agents are not required to apply to <code>table</code> and <code>inline-table</code> elements when <a href="border-collapse"><code>border-collapse</code></a> is <code>collapse</code>. The behavior on internal table elements is undefined for the moment.. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the corresponding dimension of the border box</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>two absolute <a href="length"><code>&lt;length&gt;</code></a>s or <a href="percentage"><code>&lt;percentage&gt;</code></a>s</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <length-percentage>{1,2}where
    <length-percentage> = <length> | <percentage>

## Examples

### Border radius with vertical text

#### HTML

    <div>
      <p class="exampleText">Example</p>
    </div>

#### CSS

    div {
      background-color: rebeccapurple;
      width: 120px;
      height: 120px;
      border-start-end-radius: 10px;
    }

    .exampleText {
      writing-mode: vertical-rl;
      padding: 10px;
      background-color: #fff;
      border-start-end-radius: 10px;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-border-start-end-radius">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'border-start-end-radius' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`border-start-end-radius`

89

89

66

No

75

No

89

89

66

No

No

No

## See also

- The mapped physical property: [`border-bottom-left-radius`](border-bottom-left-radius)
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-start-end-radius" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-start-end-radius</a>
