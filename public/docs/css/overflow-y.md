# overflow-y

The `overflow-y` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets what shows when content overflows a block-level element's top and bottom edges. This may be nothing, a scroll bar, or the overflow content.

## Syntax

    /* Keyword values */
    overflow-y: visible;
    overflow-y: hidden;
    overflow-y: clip;
    overflow-y: scroll;
    overflow-y: auto;

    /* Global values */
    overflow-y: inherit;
    overflow-y: initial;
    overflow-y: unset;

The `overflow-y` property is specified as a single keyword chosen from the list of values below.

If [`overflow-x`](overflow-x) is `hidden`, `scroll` or `auto` and this property is `visible` (default) it will implicitly compute to `auto`.

### Values

`visible`  
Content is not clipped and may be rendered outside the padding box's top and bottom edges.

`hidden`  
Content is clipped if necessary to fit vertically in the padding box. No scrollbars are provided.

`clip` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Like for `hidden`, the content is clipped to the element's padding box. The difference between `clip` and `hidden` is that the `clip` keyword also forbids all scrolling, including programmatic scrolling. The box is not a scroll container, and does not start a new formatting context. If you wish to start a new formatting context, you can use [`display: flow-root`](display#flow-root) to do so.

`scroll`  
Content is clipped if necessary to fit vertically in the padding box. Browsers display scrollbars whether or not any content is actually clipped. (This prevents scrollbars from appearing or disappearing when the content changes.) Printers may still print overflowing content.

`auto`  
Depends on the user agent. If content fits inside the padding box, it looks the same as `visible`, but still establishes a new block-formatting context. Desktop browsers provide scrollbars if content overflows.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>visible</code></td></tr><tr class="even"><td>Applies to</td><td>Block-containers, flex containers, and grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified, except with <code>visible</code>/<code>clip</code> computing to <code>auto</code>/<code>hidden</code> respectively if one of <a href="overflow-x"><code>overflow-x</code></a> or <a href="overflow-y"><code>overflow-y</code></a> is neither <code>visible</code> nor clip</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    visible | hidden | clip | scroll | auto

## Examples

### Setting overflow-y behavior

#### HTML

    <ul>
      <li><code>overflow-y:hidden</code> — hides the text outside the box
      <div id="div1">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
        </div>
      </li>

      <li><code>overflow-y:scroll</code> — always adds a scrollbar
      <div id="div2">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
        </div>
      </li>

      <li><code>overflow-y:visible</code> — displays the text outside the box if needed
      <div id="div3">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
        </div>
      </li>

      <li><code>overflow-y:auto</code> — on most browser, equivalent to <code>scroll</code>
      <div id="div4">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
        </div>
      </li>
    </ul>

#### CSS

    #div1,
    #div2,
    #div3,
    #div4 {
      border: 1px solid black;
      width:  250px;
      height: 100px;
    }

    #div1 { overflow-y: hidden; margin-bottom: 12px;}
    #div2 { overflow-y: scroll; margin-bottom: 12px;}
    #div3 { overflow-y: visible; margin-bottom: 120px;}
    #div4 { overflow-y: auto; margin-bottom: 120px;}

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overflow-3/#propdef-overflow-y">CSS Overflow Module Level 3<br />
<span class="small">The definition of 'overflow-y' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`overflow-y`

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

- Related CSS properties: [`text-overflow`](text-overflow), [`white-space`](white-space), [`overflow`](overflow), [`overflow-x`](overflow-x), [`clip`](clip), [`display`](display)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-y</a>
