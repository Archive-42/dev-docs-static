# background-blend-mode

The `background-blend-mode` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how an element's background images should blend with each other and with the element's background color.

Blending modes should be defined in the same order as the [`background-image`](background-image) property. If the blending modes' and background images' list lengths are not equal, it will be repeated and/or truncated until lengths match.

## Syntax

    /* One value */
    background-blend-mode: normal;

    /* Two values, one per background */
    background-blend-mode: darken, luminosity;

    /* Global values */
    background-blend-mode: initial;
    background-blend-mode: inherit;
    background-blend-mode: unset;

### Values

[`<blend-mode>`](blend-mode)  
The blending mode to be applied. There can be several values, separated by commas.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>All elements. In SVG, it applies to container elements, graphics elements, and graphics referencing elements.. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <blend-mode>#where
    <blend-mode> = normal | multiply | screen | overlay | darken | lighten | color-dodge | color-burn | hard-light | soft-light | difference | exclusion | hue | saturation | color | luminosity

## Examples

### Basic example

    .item {
        width: 300px;
        height: 300px;
        background: url('image1.png'),url('image2.png');
        background-blend-mode: screen;
    }

### Try out different blend modes

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/compositing-1/#background-blend-mode">Compositing and Blending Level 1<br />
<span class="small">The definition of 'background-blend-mode' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`background-blend-mode`

35

79

30

No

22

8

≤37

35

30

22

8

3.0

## See also

- [`<blend-mode>`](blend-mode)
- [`mix-blend-mode`](mix-blend-mode)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-blend-mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/background-blend-mode</a>
