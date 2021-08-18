# overscroll-behavior-block

The `overscroll-behavior-block` CSS property sets the browser's behavior when the block direction boundary of a scrolling area is reached.

See [`overscroll-behavior`](overscroll-behavior) for a full explanation.

    /* Keyword values */
    overscroll-behavior-block: auto; /* default */
    overscroll-behavior-block: contain;
    overscroll-behavior-block: none;

    /* Global values */
    overscroll-behavior-block: inherit;
    overscroll-behavior-block: initial;
    overscroll-behavior-block: unset;

## Syntax

The `overscroll-behavior-block` property is specified as a keyword chosen from the list of values below.

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

### Preventing block overscrolling

In this demo we have two block-level boxes, one inside the other. The outer box has a large [`height`](height) set on it so the page will scroll vertically. The inner box has a small [`width`](width) (and `height`) set on it so it sits comfortably inside the viewport, but its content is given a large `height` so it will also scroll vertically.

By default, when the inner box is scrolled and a scroll boundary is reached, the whole page will begin to scroll, which is probably not what we want. To avoid this happening in the block direction, we've set `overscroll-behavior-block: contain` on the inner box.

#### HTML

    <main>
      <div>
        <div>
          <p><code>overscroll-behavior-block</code> has been used to make it so that when the scroll boundaries of the yellow inner box are reached, the whole page does not begin to scroll.</p>
        </div>
      </div>
    </main>

#### CSS

    main {
      height: 3000px;
      width: 500px;
      background-color: white;
      background-image: repeating-linear-gradient(to bottom, rgba(0,0,0,0) 0px, rgba(0,0,0,0) 19px, rgba(0,0,0,0.5) 20px);
    }

    main > div {
      height: 300px;
      width: 400px;
      overflow: auto;
      position: relative;
      top: 50px;
      left: 50px;
      overscroll-behavior-block: contain;
    }

    div > div {
      height: 1500px;
      width: 100%;
      background-color: yellow;
      background-image: repeating-linear-gradient(to bottom, rgba(0,0,0,0) 0px, rgba(0,0,0,0) 19px, rgba(0,0,0,0.5) 20px);
    }

    p {
      padding: 10px;
      background-color: rgba(255,0,0,0.5);
      margin: 0;
      width: 340px;
      position: relative;
      top: 10px;
      left: 10px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overscroll-1/#propdef-overscroll-behavior-block">CSS Overscroll Behavior Module Level 1<br />
<span class="small">The definition of 'overscroll-behavior-block' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`overscroll-behavior-block`

77

79

73

No

64

No

See [bug 176454](https://webkit.org/b/176454).

77

77

No

55

No

See [bug 176454](https://webkit.org/b/176454).

12.0

## See also

- [Take control of your scroll: customizing pull-to-refresh and overflow effects](https://developers.google.com/web/updates/2017/11/overscroll-behavior#demo)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-block" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-block</a>
