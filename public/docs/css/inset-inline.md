# inset-inline

The `inset-inline` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the logical start and end offsets of an element in the inline direction, which maps to physical offsets depending on the element's writing mode, directionality, and text orientation. It corresponds to the [`top`](top) and [`bottom`](bottom), or [`right`](right) and [`left`](left) properties depending on the values defined for [`writing-mode`](writing-mode), [`direction`](direction), and [`text-orientation`](text-orientation).

    /* <length> values */
    inset-inline: 3px 10px;
    inset-inline: 2.4em 3em;
    inset-inline: 10px; /* value applied to start and end */

    /* <percentage>s of the width or height of the containing block */
    inset-inline: 10% 5%;

    /* Keyword value */
    inset-inline: auto;

    /* Global values */
    inset-inline: inherit;
    inset-inline: initial;
    inset-inline: unset;

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`inset-inline-end`](inset-inline-end)
- [`inset-inline-start`](inset-inline-start)

## Syntax

### Values

The `inset-inline` property takes the same values as the [`left`](left) property.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>positioned elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>logical-width of containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>same as box offsets: <a href="top"><code>top</code></a>, <a href="right"><code>right</code></a>, <a href="bottom"><code>bottom</code></a>, <a href="left"><code>left</code></a> properties except that directions are logical</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <'top'>{1,2}

## Examples

### Setting inline start and end offsets

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
      position: relative;
      inset-inline: 20px 50px;
      background-color: #c8c800;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#propdef-inset-inline">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'inset-inline' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`inset-inline`

87

69

79

63

41-63

No

73

56

14.1

87

87

69

63

41-63

48

14.5

No

## See also

- The mapped physical properties: [`top`](top), [`right`](right), [`bottom`](bottom), and [`left`](left)
- The mapped physical shortcut: [`inset`](inset)
- The mapped block shortcut: [`inset-block`](inset-block)
- [`writing-mode`](writing-mode), [`direction`](direction), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/inset-inline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/inset-inline</a>
