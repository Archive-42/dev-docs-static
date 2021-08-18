# max-inline-size

The `max-inline-size` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the horizontal or vertical maximum size of an element's block, depending on its writing mode. It corresponds to either the [`max-width`](max-width) or the [`max-height`](max-height) property, depending on the value of [`writing-mode`](writing-mode).

If the writing mode is vertically oriented, the value of `max-inline-size` relates to the maximal height of the element; otherwise, it relates to the maximal width of the element. A related property is [`max-block-size`](max-block-size), which defines the other dimension of the element.

## Syntax

    /* <length> values */
    max-inline-size: 300px;
    max-inline-size: 25em;

    /* <percentage> values */
    max-inline-size: 75%;

    /* Keyword values */
    max-inline-size: auto;
    max-inline-size: max-content;
    max-inline-size: min-content;
    max-inline-size: fit-content(20em);

    /* Global values */
    max-inline-size: inherit;
    max-inline-size: initial;
    max-inline-size: unset;

### Values

The `max-inline-size` property takes the same values as the [`max-width`](max-width) and [`max-height`](max-height) properties.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>same as <a href="width"><code>width</code></a> and <a href="height"><code>height</code></a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>inline-size of containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>same as <a href="max-width"><code>max-width</code></a> and <a href="max-height"><code>max-height</code></a></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <'max-width'>

## Examples

### Setting maximum inline size in pixels

#### HTML

    <p class="exampleText">Example text</p>

#### CSS

    .exampleText {
      writing-mode: vertical-rl;
      background-color: yellow;
      block-size: 100%;
      max-inline-size: 200px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-max-inline-size">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'max-inline-size' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`max-inline-size`

57

79

41

No

44

12.1

10.1

57

57

41

43

12.2

10.3

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

- The mapped physical properties: [`max-width`](max-width) and [`max-height`](max-height)
- [`writing-mode`](writing-mode)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/max-inline-size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/max-inline-size</a>
