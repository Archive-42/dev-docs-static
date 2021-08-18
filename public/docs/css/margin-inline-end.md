# margin-inline-end

The `margin-inline-end` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the logical inline end margin of an element, which maps to a physical margin depending on the element's writing mode, directionality, and text orientation. In other words, it corresponds to the [`margin-top`](margin-top), [`margin-right`](margin-right), [`margin-bottom`](margin-bottom) or [`margin-left`](margin-left) property depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

## Syntax

    /* <length> values */
    margin-inline-end: 10px;   /* An absolute length */
    margin-inline-end: 1em;    /* relative to the text size */
    margin-inline-end: 5%;     /* relative to the nearest block container's width */

    /* Keyword values */
    margin-inline-end: auto;

    /* Global values */
    margin-inline-end: inherit;
    margin-inline-end: initial;
    margin-inline-end: unset;

It relates to [`margin-block-start`](margin-block-start), [`margin-block-end`](margin-block-end), and [`margin-inline-start`](margin-inline-start), which define the other margins of the element.

### Values

The `margin-inline-end` property takes the same values as the [`margin-left`](margin-left) property.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>same as <a href="margin"><code>margin</code></a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>depends on layout model</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>if specified as a length, the corresponding absolute length; if specified as a percentage, the specified value; otherwise, <code>auto</code></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <'margin-left'>

## Examples

### Setting inline end margin

#### HTML

    <div>
      <p class="exampleText">Example text</p>
    </div>

#### CSS

    div {
      background-color: yellow;
      width: 120px;
      height: 120px;
    }

    .exampleText {
      writing-mode: vertical-lr;
      margin-inline-end: 20px;
      background-color: #c8c800;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-margin-inline-end">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'margin-inline-end' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`margin-inline-end`

69

2

79

79

41

3

No

56

15

12.1

3

69

2

69

18

41

4

48

14

12.2

3

10.0

1.0

## See also

- [`margin-inline-start`](margin-inline-start)
- The mapped physical properties: [`margin-top`](margin-top), [`margin-right`](margin-right), [`margin-bottom`](margin-bottom), and [`margin-left`](margin-left)
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline-end" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline-end</a>
