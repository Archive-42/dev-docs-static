# block-size

The `block-size` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the horizontal or vertical size of an element's block, depending on its writing mode. It corresponds to either the [`width`](width) or the [`height`](height) property, depending on the value of [`writing-mode`](writing-mode).

If the writing mode is vertically oriented, the value of `block-size` relates to the width of the element; otherwise, it relates to the height of the element. A related property is [`inline-size`](inline-size), which defines the other dimension of the element.

## Syntax

    /* <length> values */
    block-size: 300px;
    block-size: 25em;

    /* <percentage> values */
    block-size: 75%;

    /* Keyword values */
    block-size: max-content;
    block-size: min-content;
    block-size: fit-content(20em);
    block-size: auto;

    /* Global values */
    block-size: inherit;
    block-size: initial;
    block-size: unset;

### Values

The `block-size` property takes the same values as the [`width`](width) and [`height`](height) properties.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>same as <a href="width"><code>width</code></a> and <a href="height"><code>height</code></a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>block-size of containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>same as <a href="width"><code>width</code></a> and <a href="height"><code>height</code></a></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <'width'>

## Examples

### Block size with vertical text

#### HTML

    <p class="exampleText">Example text</p>

#### CSS

    .exampleText {
      writing-mode: vertical-rl;
      background-color: yellow;
      block-size: 200px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-block-size">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'block-size' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`block-size`

57

79

41

No

44

12.1

57

57

41

43

12.2

5.0

`fit-content`

57

79

41

No

44

12.1

57

57

41

43

12.2

5.0

`max-content`

57

79

66

41

No

44

12.1

57

57

66

41

43

12.2

5.0

`min-content`

57

79

66

41

No

44

12.1

57

57

66

41

43

12.2

5.0

## See also

- The mapped physical properties: [`width`](width) and [`height`](height)
- [`writing-mode`](writing-mode)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/block-size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/block-size</a>
