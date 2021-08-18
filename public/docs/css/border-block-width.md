# border-block-width

The `border-block-width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the width of the logical block borders of an element, which maps to a physical border width depending on the element's writing mode, directionality, and text orientation. It corresponds to the [`border-top-width`](border-top-width) and [`border-bottom-width`](border-bottom-width), or [`border-left-width`](border-left-width), and [`border-right-width`](border-right-width) property depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

    /* <'border-width'> values */
    border-block-width: 5px;
    border-block-width: thick;

The border width in the other dimension can be set with [`border-inline-width`](border-inline-width), which sets [`border-inline-start-width`](border-inline-start-width), and [`border-inline-end-width`](border-inline-end-width).

## Syntax

### Values

`<'border-width'>`  
The width of the border. See [`border-width`](border-width).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>medium</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>logical-width of containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>absolute length; <code>0</code> if the border style is <code>none</code> or <code>hidden</code></td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'border-top-width'>

## Examples

### Border width with vertical text

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
      border: 1px solid blue;
      border-block-width: 5px;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-border-block-width">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'border-block-width' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-block-width`

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

No

48

14.5

No

## See also

- This property maps to one of the physical border properties: [`border-top-width`](border-top-width), [`border-right-width`](border-right-width), [`border-bottom-width`](border-bottom-width), and [`border-left-width`](border-left-width)
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-width</a>
