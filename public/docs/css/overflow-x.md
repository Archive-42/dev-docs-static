# overflow-x

The `overflow-x` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets what shows when content overflows a block-level element's left and right edges. This may be nothing, a scroll bar, or the overflow content.

## Syntax

    /* Keyword values */
    overflow-x: visible;
    overflow-x: hidden;
    overflow-x: clip;
    overflow-x: scroll;
    overflow-x: auto;

    /* Global values */
    overflow-x: inherit;
    overflow-x: initial;
    overflow-x: unset;

The `overflow-x` property is specified as a single keyword chosen from the list of values below.

### Values

`visible`  
Content is not clipped and may be rendered outside the padding box's left and right edges. If [`overflow-y`](overflow-y) is `hidden`, `scroll` or `auto` and this property is `visible`, it will implicitly compute to `auto`.

`hidden`  
Content is clipped if necessary to fit horizontally in the padding box. No scrollbars are provided.

`clip` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Like for `hidden`, the content is clipped to the element's padding box. The difference between `clip` and `hidden` is that the `clip` keyword also forbids all scrolling, including programmatic scrolling. The box is not a scroll container, and does not start a new formatting context. If you wish to start a new formatting context, you can use [`display: flow-root`](display#flow-root) to do so.

`scroll`  
Content is clipped if necessary to fit horizontally in the padding box. Browsers display scrollbars whether or not any content is actually clipped. (This prevents scrollbars from appearing or disappearing when the content changes.) Printers may still print overflowing content.

`auto`  
Depends on the user agent. If content fits inside the padding box, it looks the same as `visible`, but still establishes a new block-formatting context. Desktop browsers provide scrollbars if content overflows.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>visible</code></td></tr><tr class="even"><td>Applies to</td><td>Block-containers, flex containers, and grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified, except with <code>visible</code>/<code>clip</code> computing to <code>auto</code>/<code>hidden</code> respectively if one of <a href="overflow-x"><code>overflow-x</code></a> or <a href="overflow-y"><code>overflow-y</code></a> is neither <code>visible</code> nor clip</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    visible | hidden | clip | scroll | auto

## Examples

### HTML

    <ul>
      <li><code>overflow-x:hidden</code> — hides the text outside the box
        <div id="div1">
          ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
        </div>
      </li>

      <li><code>overflow-x:scroll</code> — always adds a scrollbar
        <div id="div2">
          ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
        </div>
      </li>

      <li><code>overflow-x:visible</code> — displays the text outside the box if needed
        <div id="div3">
          ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
        </div>
      </li>

      <li><code>overflow-x:auto</code> — on most browsers, equivalent to <code>scroll</code>
        <div id="div4">
          ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
        </div>
      </li>
    </ul>

### CSS

    #div1, #div2, #div3, #div4 {
      border: 1px solid black;
      width:  250px;
      margin-bottom: 12px;
    }

    #div1 { overflow-x: hidden;}
    #div2 { overflow-x: scroll;}
    #div3 { overflow-x: visible;}
    #div4 { overflow-x: auto;}

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overflow-3/#propdef-overflow-x">CSS Overflow Module Level 3<br />
<span class="small">The definition of 'overflow-x' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`overflow-x`

1

12

3.5

5

8

9.5

3

1

18

4

14

1

1.0

`clip`

No

No

81

3.5-81

No

No

No

No

No

81

4-81

No

No

No

## See also

- Related CSS properties: [`text-overflow`](text-overflow), [`white-space`](white-space), [`overflow`](overflow), [`overflow-y`](overflow-y), [`clip`](clip), [`display`](display)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x</a>
