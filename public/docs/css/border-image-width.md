# border-image-width

The `border-image-width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the width of an element's [border image](border-image).

If this property's value is greater than the element's [`border-width`](border-width), the border image will extend beyond the padding (and/or content) edge.

## Syntax

    /* Keyword value */
    border-image-width: auto;

    /* <length> value */
    border-image-width: 1rem;

    /* <percentage> value */
    border-image-width: 25%;

    /* <number> value */
    border-image-width: 3;

    /* vertical | horizontal */
    border-image-width: 2em 3em;

    /* top | horizontal | bottom */
    border-image-width: 5% 15% 10%;

    /* top | right | bottom | left */
    border-image-width: 5% 2em 10% auto;

    /* Global values */
    border-image-width: inherit;
    border-image-width: initial;
    border-image-width: unset;

The `border-image-width` property may be specified using one, two, three, or four values chosen from the list of values below.

- When **one** value is specified, it applies the same width to **all four sides**.
- When **two** values are specified, the first width applies to the **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first width applies to the **top**, the second to the **left and right**, the third to the **bottom**.
- When **four** values are specified, the widths apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

### Values

`<length-percentage>`  
The width of the border, specified as a [`<length>`](length) or a [`<percentage>`](percentage). Percentages are relative to the _width_ of the border image area for horizontal offsets and the _height_ of the border image area for vertical offsets. Must not be negative.

`<number>`  
The width of the border, specified as a multiple of the corresponding [`border-width`](border-width). Must not be negative.

`auto`  
The width of the border is made equal to the intrinsic width or height (whichever is applicable) of the corresponding [`border-image-slice`](border-image-slice). If the image does not have the required intrinsic dimension, the corresponding `border-width` is used instead.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>1</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, except internal table elements when <a href="border-collapse"><code>border-collapse</code></a> is <code>collapse</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width or height of the border image area</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="even"><td>Animation type</td><td>by computed value type</td></tr></tbody></table>

## Formal syntax

    [ <length-percentage> | <number> | auto ]{1,4}where
    <length-percentage> = <length> | <percentage>

## Examples

### Tiling a border image

This example creates a border image using the following ".png" file, which is 90 by 90 pixels:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAABaBAMAAADKhlwxAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAkUExURf///wAz/5lm/8yZ/8zM/2aZ/zNm/2Zm/5mZ/5nM/zMz/8z//9+o9/4AAAGUSURBVFjD7ZaxTsMwFEUNpaISC5ZCSzfkMjBWER9AQeytxAJbP4E/KPxBBhZ2hm58InFCEr/j2JI7dcjdns5N8mL7XVkpq6dPs7hXrb62evrSlaCPxmrRlB/a6idA69KY27osdK2sl45Mo6Utz3WjdQ9VeVtXX9u07lkP7R6uHu9eXb0ctO3rv7fCcc89qowrpbQrj45EvZwI9xpUnYr65kS4L0FFY2VrK+HOQJ0VqlZpI9xXoHRvhXtKt5HSUqBH5E77y7QVTNudtJ0/E/WDPFU70MQTy/PuNp7505A2aZzT9+gUMwPG8YRgvjSd73tp87W2fKvM17/9tMzF3Nw5ufhcpuZrkFo8c0IVkvQCoSpF+i1DFQJFqEKkCFUIFFsdfHVNEaoQKY4oBIpQhZkUowU3aSHHNtK2pYiE4PrVFHEDNymiLLYkJT0ed9pfpq3gKro7pGk7j1CNnqpd4ollqEYaz5InjaEKkY6jCeFRhGqg830gVCGPIlT91BS0zNzYPTYf7rHDPXa4xw732OEee8g99g8YvlZi9f5jWgAAAABJRU5ErkJggg==" width="90" height="90" />

Thus, each circle in the source image is 30 by 30 pixels.

#### HTML

    <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
       eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.
       At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren,
       no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>

#### CSS

    p {
      border: 20px solid;
      border-image: url("https://mdn.mozillademos.org/files/10470/border.png") 30 round;
      border-image-width: 16px;
      padding: 40px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-border-image-width">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-image-width' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-image-width`

15

12

13

11

15

6

≤37

18

14

14

6

1.0

## See also

- [Backgrounds and borders](css_backgrounds_and_borders)
- [Learn CSS: Backgrounds and borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width</a>
