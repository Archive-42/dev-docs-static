# border-block-end-color

The `border-block-end-color` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the color of the logical block-end border of an element, which maps to a physical border color depending on the element's writing mode, directionality, and text orientation. It corresponds to the [`border-top-color`](border-top-color), [`border-right-color`](border-right-color), [`border-bottom-color`](border-bottom-color), or [`border-left-color`](border-left-color) property depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

## Syntax

    border-block-end-color: yellow;
    border-block-end-color: #F5F6F7;

Related properties are [`border-block-start-color`](border-block-start-color), [`border-inline-start-color`](border-inline-start-color), and [`border-inline-end-color`](border-inline-end-color), which define the other border colors of the element.

### Values

`<'color'>`  
The color of the border. See [`color`](color).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>currentcolor</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>computed color</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

## Formal syntax

    <'border-top-color'>

## Examples

### Border color with vertical text

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
      border: 10px solid blue;
      border-block-end-color: red;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-border-block-end-color">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'border-block-end-color' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-block-end-color`

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

- This property maps to one of the physical border properties: [`border-top-color`](border-top-color), [`border-right-color`](border-right-color), [`border-bottom-color`](border-bottom-color), or [`border-left-color`](border-left-color).
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-color</a>
