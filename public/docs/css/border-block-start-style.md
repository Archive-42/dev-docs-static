# border-block-start-style

The `border-block-start-style` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the style of the logical block start border of an element, which maps to a physical border style depending on the element's writing mode, directionality, and text orientation. It corresponds to the [`border-top-style`](border-top-style), [`border-right-style`](border-right-style), [`border-bottom-style`](border-bottom-style), or [`border-left-style`](border-left-style) property depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

## Syntax

    /* <'border-style'> values */
    border-block-start-style: dashed;
    border-block-start-style: dotted;
    border-block-start-style: groove;

Related properties are [`border-block-end-style`](border-block-end-style), [`border-inline-start-style`](border-inline-start-style), and [`border-inline-end-style`](border-inline-end-style), which define the other border styles of the element.

### Values

`<'border-style'>`  
The line style of the border. See [`border-style`](border-style).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'border-top-style'>

## Examples

### Dashed border with vertical text

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
      border: 5px solid blue;
      border-block-start-style: dashed;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-border-block-start-style">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'border-block-start-style' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-block-start-style`

69

79

41

No

56

12.1

69

69

41

48

12.2

10.0

## See also

- This property maps to one of the physical border properties: [`border-top-style`](border-top-style), [`border-right-style`](border-right-style), [`border-bottom-style`](border-bottom-style), or [`border-left-style`](border-left-style).
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start-style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start-style</a>
