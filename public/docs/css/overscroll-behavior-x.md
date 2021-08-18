# overscroll-behavior-x

The `overscroll-behavior-x` CSS property sets the browser's behavior when the horizontal boundary of a scrolling area is reached.

See [`overscroll-behavior`](overscroll-behavior) for a full explanation.

    /* Keyword values */
    overscroll-behavior-x: auto; /* default */
    overscroll-behavior-x: contain;
    overscroll-behavior-x: none;

    /* Global values */
    overscroll-behavior-x: inherit;
    overscroll-behavior-x: initial;
    overscroll-behavior-x: unset;

## Syntax

The `overscroll-behavior-x` property is specified as a keyword chosen from the list of values below.

### Values

`auto`  
The default scroll overflow behavior occurs as normal.

`contain`  
Default scroll overflow behavior is observed inside the element this value is set on (e.g. "bounce" effects or refreshes), but no scroll chaining occurs to neighboring scrolling areas, e.g. underlying elements will not scroll.

`none`  
No scroll chaining occurs to neighboring scrolling areas, and default scroll overflow behavior is prevented.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>non-replaced block-level elements and non-replaced inline-block elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    contain | none | auto

## Examples

### Preventing an underlying element from scrolling horizontally

In our simple [overscroll-behavior-x example](https://mdn.github.io/css-examples/overscroll-behavior/overscroll-behavior-x) (see [source code](https://github.com/mdn/css-examples/blob/master/overscroll-behavior/overscroll-behavior-x.html) also), we have two block-level boxes, one inside the other. The outer box has a large [`width`](width) set on it so the page will scroll horizontally. The inner box has a small width (and [`height`](height)) set on it so it sits comfortably inside the viewport, but its content is given a large `width` so it will scroll horizontally.

By default, when the inner box is scrolled and a scroll boundary is reached, the whole page will begin to scroll, which is probably not what we want. To avoid this, you can set `overscroll-behavior-x: contain` on the inner box:

    main > div {
      height: 300px;
      width: 500px;
      overflow: auto;
      position: relative;
      top: 100px;
      left: 100px;
      overscroll-behavior-x: contain;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overscroll-1/#propdef-overscroll-behavior-x">CSS Overscroll Behavior Module Level 1<br />
<span class="small">The definition of 'overscroll-behavior-x' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`overscroll-behavior-x`

63

18

Currently the `none` value incorrectly behaves as `contain` (allowing for the elastic bounce effect).

59

No

50

No

See [bug 176454](https://webkit.org/b/176454).

63

63

59

46

No

See [bug 176454](https://webkit.org/b/176454).

8.0

## See also

- [Take control of your scroll: customizing pull-to-refresh and overflow effects](https://developers.google.com/web/updates/2017/11/overscroll-behavior#demo)
- The mapped logical properties: [`overscroll-behavior-inline`](overscroll-behavior-inline), [`overscroll-behavior-block`](overscroll-behavior-block)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x</a>
