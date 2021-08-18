# background-position-x

The `background-position-x` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the initial horizontal position for each background image. The position is relative to the position layer set by [`background-origin`](background-origin).

The value of this property is overridden by any declaration of the [`background`](background) or [`background-position`](background-position) shorthand properties applied to the element after it.

## Syntax

    /* Keyword values */
    background-position-x: left;
    background-position-x: center;
    background-position-x: right;

    /* <percentage> values */
    background-position-x: 25%;

    /* <length> values */
    background-position-x: 0px;
    background-position-x: 1cm;
    background-position-x: 8em;

    /* Side-relative values */
    background-position-x: right 3px;
    background-position-x: left 25%;

    /* Multiple values */
    background-position-x: 0px, center;

    /* Global values */
    background-position-x: inherit;
    background-position-x: initial;
    background-position-x: unset;

The `background-position-x` property is specified as one or more values, separated by commas.

### Values

`left`  
Aligns the left edge of the background image with the left edge of the background position layer.

`center`  
Aligns the center of the background image with the center of the background position layer.

`right`  
Aligns the right edge of the background image with the right edge of the background position layer.

[`<length>`](length)  
The offset of the given background image's left vertical edge from the background position layer's left vertical edge. (Some browsers allow assigning the right edge for offset).

[`<percentage>`](percentage)  
The offset of the given background image's horizontal position relative to the container. A value of 0% means that the left edge of the background image is aligned with the left edge of the container, and a value of 100% means that the _right_ edge of the background image is aligned with the _right_ edge of the container, thus a value of 50% horizontally centers the background image.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>left</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to width of background positioning area minus height of background image</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>A list, each item consisting of: an offset given as a combination of an absolute length and a percentage, plus an origin keyword</td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ center | [ [ left | right | x-start | x-end ]? <length-percentage>? ]! ]#where
    <length-percentage> = <length> | <percentage>

## Examples

### Basic example

The following example shows a simple background image implementation, with background-position-x and background-position-y used to define the image's horizontal and vertical positions separately.

#### HTML

    <div></div>

#### CSS

    div {
      width: 300px;
      height: 300px;
      background-color: skyblue;
      background-image: url(https://media.prod.mdn.mozit.cloud/attachments/2020/07/29/17350/3b4892b7e820122ac6dd7678891d4507/firefox.png);
      background-repeat: no-repeat;
      background-position-x: center;
      background-position-y: bottom 10px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-4/#background-position-longhands">CSS Backgrounds and Borders Module Level 4<br />
<span class="small">The definition of 'background-position-x' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial specification of longhand sub-properties of <a href="background-position"><code>background-position</code></a> to match longstanding implementations.</td></tr></tbody></table>

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

`background-position-x`

1

12

49

6

15

1

≤37

18

49

18

1

1.0

`two_value_syntax`

No

12-79

49

9

No

No

No

No

49

No

No

No

## See also

- [`background-position`](background-position)
- [`background-position-y`](background-position-y)
- <span class="page-not-created">`background-position-inline`</span>
- <span class="page-not-created">`background-position-block`</span>
- [Using multiple backgrounds](css_backgrounds_and_borders/using_multiple_backgrounds)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-position-x" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/background-position-x</a>
