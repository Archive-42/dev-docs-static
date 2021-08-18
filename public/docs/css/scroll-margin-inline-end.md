# scroll-margin-inline-end

The `scroll-margin-inline-end` property defines the margin of the scroll snap area at the end of the inline dimension that is used for snapping this box to the snapport. The scroll snap area is determined by taking the transformed border box, finding its rectangular bounding box (axis-aligned in the scroll container’s coordinate space), then adding the specified outsets.

## Syntax

    /* <length> values */
    scroll-margin-inline-end: 10px;
    scroll-margin-inline-end: 1em;

    /* Global values */
    scroll-margin-inline-end: inherit;
    scroll-margin-inline-end: initial;
    scroll-margin-inline-end: unset;

### Values

`<length>`  
An outset from the inline end edge of the scroll container.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>by computed value type</td></tr></tbody></table>

## Formal syntax

    <length>

## Examples

### Simple demonstration

This example implements something very similar to the interactive example above, except that here we'll explain to you how it's implemented.

The aim here is to create four horizontally-scrolling blocks, the second and third of which snap into place, near but not quite at the right of each block.

#### HTML

The HTML that represents the blocks is very simple:

    <div class="scroller">
      <div>1</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
    </div>

#### CSS

Let's walk through the CSS. the outer container is styled like this:

    .scroller {
      text-align: left;
      width: 250px;
      height: 250px;
      overflow-x: scroll;
      display: flex;
      box-sizing: border-box;
      border: 1px solid #000;
      scroll-snap-type: x mandatory;
    }

The main parts relevant to the scroll snapping are `overflow-x: scroll`, which makes sure the contents will scroll and not be hidden, and `scroll-snap-type: x mandatory`, which dictates that scroll snapping must occur along the horizontal axis, and the scrolling will always come to rest on a snap point.

The child elements are styled as follows:

    .scroller > div {
      flex: 0 0 250px;
      width: 250px;
      background-color: #663399;
      color: #fff;
      font-size: 30px;
      display: flex;
      align-items: center;
      justify-content: center;
      scroll-snap-align: end;
    }

    .scroller > div:nth-child(2n) {
      background-color: #fff;
      color: #663399;
    }

The most relevant part here is `scroll-snap-align: end`, which specifies that the right-hand edges (the "ends" along the x axis, in our case) are the designated snap points.

Last of all we specify the scroll margin values, a different one for the second and third child elements:

    .scroller > div:nth-child(2) {
      scroll-margin-inline-end: 1rem;
    }

    .scroller > div:nth-child(3) {
      scroll-margin-inline-end: 2rem;
    }

This means that when scrolling past the middle child elements, the scrolling will snap to `1rem` outside the inline end edge of the second `<div>`, and `2rems` outside the inline end edge of the third `<div>`.

#### Result

Try it for yourself:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scroll-snap-1/#propdef-scroll-margin-inline-end">CSS Scroll Snap Module Level 1<br />
<span class="small">The definition of 'scroll-margin-inline-end' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`scroll-margin-inline-end`

69

79

68

No

56

14.1

69

69

68

48

14.5

10.0

## See also

- [CSS Scroll Snap](css_scroll_snap)
- [Well-Controlled Scrolling with CSS Scroll Snap](https://developers.google.com/web/updates/2018/07/css-scroll-snap)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-inline-end" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-inline-end</a>
