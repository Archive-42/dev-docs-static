# border-inline-color

The `border-inline-color` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the color of the logical inline borders of an element, which maps to a physical border color depending on the element's writing mode, directionality, and text orientation. It corresponds to the [`border-top-color`](border-top-color) and [`border-bottom-color`](border-bottom-color), or [`border-right-color`](border-right-color) and [`border-left-color`](border-left-color) property depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

    border-inline-color: yellow;
    border-inline-color: #F5F6F7;

The border color in the other dimension can be set with [`border-block-color`](border-block-color) which sets [`border-block-start-color`](border-block-start-color), and [`border-block-end-color`](border-block-end-color).

## Syntax

### Values

`<'color'>`  
The color of the border. See [`color`](color).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>currentcolor</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>computed color</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'border-top-color'>{1,2}

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
      border-inline-color: red;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-border-inline-color">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'border-inline-color' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-inline-color`

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

- This property maps to the physical border properties: [`border-top-color`](border-top-color), [`border-right-color`](border-right-color), [`border-bottom-color`](border-bottom-color), or [`border-left-color`](border-left-color).
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)+ bug 1297097

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-color</a>
