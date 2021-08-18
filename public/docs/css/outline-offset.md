# outline-offset

The `outline-offset` CSS property sets the amount of space between an [outline](outline) and the edge or border of an element.

## Syntax

    /* <length> values */
    outline-offset: 3px;
    outline-offset: 0.2em;

    /* Global values */
    outline-offset: inherit;
    outline-offset: initial;
    outline-offset: unset;

### Values

`<length>`  
The width of the space between the element and its outline. A negative value places the outline inside the element. A value of `0` places the outline so that there is no space between it and the element.

## Description

An outline is a line that is drawn around an element, outside the border edge. The space between an element and its outline is transparent. In other words, it is the same as the parent element's background.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <length>

## Examples

### Setting outline offset in pixels

#### HTML

    <p>Gallia est omnis divisa in partes tres.</p>

#### CSS

    p {
      outline: 1px dashed red;
      outline-offset: 10px;
      background: yellow;
      border: 1px solid blue;
      margin: 15px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ui-3/#outline-offset">CSS Basic User Interface Module Level 3<br />
<span class="small">The definition of 'outline-offset' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`outline-offset`

1

15

1.5

No

9.5

1.2

37

18

4

14

1

1.0

## See also

- [`outline`](outline)
- [`outline-color`](outline-color)
- [`outline-style`](outline-style)
- [`outline-width`](outline-width)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset</a>
