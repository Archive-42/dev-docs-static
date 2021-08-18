# min-inline-size

The `min-inline-size` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the horizontal or vertical minimal size of an element's block, depending on its writing mode. It corresponds to either the [`min-width`](min-width) or the [`min-height`](min-height) property, depending on the value of [`writing-mode`](writing-mode).

## Syntax

    /* <length> values */
    min-inline-size: 100px;
    min-inline-size: 5em;

    /* <percentage> values */
    min-inline-size: 10%;

    /* Keyword values */
    min-inline-size: max-content;
    min-inline-size: min-content;
    min-inline-size: fit-content(20em);

    /* Global values */
    min-inline-size: inherit;
    min-inline-size: initial;
    min-inline-size: unset;

If the writing mode is vertically oriented, the value of `min-inline-size` relates to the minimum height of the element; otherwise, it relates to the minimum width of the element. A related property is [`min-block-size`](min-block-size), which defines the other dimension of the element.

### Values

The `min-inline-size` property takes the same values as the [`min-width`](min-width) and [`min-height`](min-height) properties.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>same as <a href="width"><code>width</code></a> and <a href="height"><code>height</code></a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>inline-size of containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>same as <a href="min-width"><code>min-width</code></a> and <a href="min-height"><code>min-height</code></a></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <'min-width'>

## Examples

### Setting minimum inline size for vertical text

#### HTML

    <p class="exampleText">Example text</p>

#### CSS

    .exampleText {
      writing-mode: vertical-rl;
      background-color: yellow;
      block-size: 5%;
      min-inline-size: 200px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-min-inline-size">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'min-inline-size' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`min-inline-size`

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

7.0

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

7.0

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

7.0

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

7.0

## See also

- The mapped physical properties: [`min-width`](min-width) and [`min-height`](min-height)
- [`writing-mode`](writing-mode)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/min-inline-size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/min-inline-size</a>
