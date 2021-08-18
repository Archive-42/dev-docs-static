# offset-anchor

The `offset-anchor` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the point inside the box of an element travelling along an [`offset-path`](offset-path) that is actually moving along the path.

## Syntax

    /* Keyword values */
    offset-anchor: top;
    offset-anchor: bottom;
    offset-anchor: left;
    offset-anchor: right;
    offset-anchor: center;
    offset-anchor: auto;

    /* <percentage> values */
    offset-anchor: 25% 75%;

    /* <length> values */
    offset-anchor: 0 0;
    offset-anchor: 1cm 2cm;
    offset-anchor: 10ch 8em;

    /* Edge offsets values */
    offset-anchor: bottom 10px right 20px;
    offset-anchor: right 3em bottom 10px;

    /* Global values */
    offset-anchor: inherit;
    offset-anchor: initial;
    offset-anchor: unset;

### Values

`auto`  
`offset-anchor` is given the same value as the element's [`transform-origin`](transform-origin), unless [`offset-path`](offset-path) is `none`, in which case it takes its value from [`offset-position`](offset-position).

`<position>`  
A [`<position>`](position_value) defines an x/y coordinate, to place an item relative to the edges of an element's box. It can be defined using one to four values. For more specifics, see the [`<position>`](position_value) and [`background-position`](background-position) reference pages. Note that the 3-value position syntax does not work for any usage of `<position>`, except for in `background(-position)`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>relativeToWidthAndHeight</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>for <a href="length"><code>&lt;length&gt;</code></a> the absolute value, otherwise a percentage</td></tr><tr class="even"><td>Animation type</td><td>a <a href="position_value#interpolation">position</a></td></tr></tbody></table>

## Formal syntax

    auto | <position>where
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]where
    <length-percentage> = <length> | <percentage>

## Examples

### Setting various offset-anchor values

In the following example, we have three [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) elements nested in [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) elements. Each `<div>` is given the same [`offset-path`](offset-path) (a horizontal line 200 pixels long) and animated to move along it. The three are then given different [`background-color`](background-color) and `offset-anchor` values.

Each `<section>` has been styled with a linear gradient to give it a horizontal line running through its center, to give you a visual display of where the `<div>`'s offset paths are running.

This allows you to see what effect the different `offset-anchor` values have — the first one, `auto`, causes the `<div>`'s center point to move along the path. The other two cause the `<div>`'s top-right and bottom-left points to move along the path, respectively.

#### HTML

    <section>
      <div class="offset-anchor1"></div>
    </section>
    <section>
      <div class="offset-anchor2"></div>
    </section>
    <section>
      <div class="offset-anchor3"></div>
    </section>

#### CSS

    div {
      offset-path: path('M 0,20 L 200,20');
      animation: move 3000ms infinite alternate ease-in-out;
      width: 40px;
      height: 40px;
    }

    section {
      background-image: linear-gradient(to bottom, transparent, transparent 49%, #000 50%, #000 51%, transparent 52%);
      border: 1px solid #ccc;
      margin-bottom: 10px;
    }

    .offset-anchor1 {
      offset-anchor: auto;
      background: cyan;
    }

    .offset-anchor2 {
      offset-anchor: right top;
      background: purple;
    }

    .offset-anchor3 {
      offset-anchor: left bottom;
      background: magenta;
    }

    @keyframes move {
      0% {
        offset-distance: 0%;
      }
      100% {
        offset-distance: 100%;
      }
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/motion-1/#offset-anchor-property">Motion Path Module Level 1<br />
<span class="small">The definition of 'offset-anchor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`offset-anchor`

79

79

72

70-72

No

No

No

79

79

No

No

No

12.0

## See also

- [`offset`](offset)
- [`offset-distance`](offset-distance)
- [`offset-rotation`](offset-rotate)
- [SVG `<path> `](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset-anchor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/offset-anchor</a>
