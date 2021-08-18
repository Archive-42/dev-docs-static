# overflow-inline

The `overflow-inline` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets what shows when content overflows the inline start and end edges of a box. This may be nothing, a scroll bar, or the overflow content.

The `overflow-inline` property maps to [`overflow-y`](overflow-y) or [`overflow-x`](overflow-x) depending on the writing mode of the document.

## Syntax

    /* Keyword values */
    overflow-inline: visible;
    overflow-inline: hidden;
    overflow-inline: scroll;
    overflow-inline: auto;

    /* Global values */
    overflow-inline: inherit;
    overflow-inline: initial;
    overflow-inline: unset;

The `overflow-inline` property is specified as a single keyword chosen from the list of values below.

### Values

`visible`  
Content is not clipped and may be rendered outside the padding box's inline start and end edges.

`hidden`  
Content is clipped if necessary to fit the inline dimension in the padding box. No scrollbars are provided.

`scroll`  
Content is clipped if necessary to fit in the padding box in the inline dimension. Browsers display scrollbars whether or not any content is actually clipped. (This prevents scrollbars from appearing or disappearing when the content changes.) Printers may still print overflowing content.

`auto`  
Depends on the user agent. If content fits inside the padding box, it looks the same as `visible`, but still establishes a new block-formatting context. Desktop browsers provide scrollbars if content overflows.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>Block-containers, flex containers, and grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified, except with <code>visible</code>/<code>clip</code> computing to <code>auto</code>/<code>hidden</code> respectively if one of <a href="overflow-x"><code>overflow-x</code></a> or <a href="overflow-y"><code>overflow-y</code></a> is neither <code>visible</code> nor clip</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    visible | hidden | clip | scroll | auto

## Examples

### Setting inline overflow behavior

#### HTML

    <ul>
      <li><code>overflow-inline:hidden</code> — hides the text outside the box
        <div id="div1">
          ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
        </div>
      </li>

      <li><code>overflow-inline:scroll</code> — always adds a scrollbar
        <div id="div2">
          ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
        </div>
      </li>

      <li><code>overflow-inline:visible</code> — displays the text outside the box if needed
        <div id="div3">
          ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
        </div>
      </li>

      <li><code>overflow-inline:auto</code> — on most browsers, equivalent to <code>scroll</code>
        <div id="div4">
          ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ
        </div>
      </li>
    </ul>

#### CSS

    #div1, #div2, #div3, #div4 {
      border: 1px solid black;
      width:  250px;
      margin-bottom: 12px;
    }

    #div1 { overflow-inline: hidden;}
    #div2 { overflow-inline: scroll;}
    #div3 { overflow-inline: visible;}
    #div4 { overflow-inline: auto;}

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overflow-3/#propdef-overflow-inline">CSS Overflow Module Level 3<br />
<span class="small">The definition of 'overflow-inline' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`overflow-inline`

No

No

69

No

No

No

No

No

No

No

No

No

## See also

- Related CSS properties: [`text-overflow`](text-overflow), [`white-space`](white-space), [`overflow`](overflow), [`overflow-block`](overflow-block), [`overflow-x`](overflow-x), [`overflow-y`](overflow-y), [`clip`](clip), [`display`](display)
- [CSS Logical Properties](css_logical_properties)
- [Writing Modes](css_writing_modes)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-inline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-inline</a>
