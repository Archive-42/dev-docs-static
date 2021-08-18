# overflow

The `overflow` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) sets the desired behavior for an element's overflow — i.e. when an element's content is too big to fit in its [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context) — in both directions.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`overflow-x`](overflow-x)
- [`overflow-y`](overflow-y)

## Syntax

    /* Keyword values */
    overflow: visible;
    overflow: hidden;
    overflow: clip;
    overflow: scroll;
    overflow: auto;
    overflow: hidden visible;

    /* Global values */
    overflow: inherit;
    overflow: initial;
    overflow: unset;

The `overflow` property is specified as one or two keywords chosen from the list of values below. If two keywords are specified, the first applies to `overflow-x` and the second to `overflow-y`. Otherwise, both `overflow-x` and `overflow-y` are set to the same value.

### Values

`visible`  
Content is not clipped and may be rendered outside the padding box.

`hidden`  
Content is clipped if necessary to fit the padding box. No scrollbars are provided, and no support for allowing the user to scroll (such as by dragging or using a scroll wheel) is allowed. The content _can_ be scrolled programmatically (for example, by setting the value of a property such as [`offsetLeft`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetLeft)), so the element is still a scroll container.

`clip`  
Like for `hidden`, the content is clipped to the element's padding box. The difference between `clip` and `hidden` is that the `clip` keyword also forbids all scrolling, including programmatic scrolling. The box is not a scroll container, and does not start a new formatting context. If you wish to start a new formatting context, you can use [`display: flow-root`](display#flow-root) to do so.

`scroll`  
Content is clipped if necessary to fit the padding box. Browsers always display scrollbars whether or not any content is actually clipped, preventing scrollbars from appearing or disappearing as content changes. Printers may still print overflowing content.

`auto`  
Depends on the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent). If content fits inside the padding box, it looks the same as `visible`, but still establishes a new block formatting context. Desktop browsers provide scrollbars if content overflows.

`overlay` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Behaves the same as `auto`, but with the scrollbars drawn on top of content instead of taking up space. Only supported in WebKit-based (e.g., Safari) and Blink-based (e.g., Chrome or Opera) browsers.

#### Mozilla extensions

`-moz-scrollbars-none` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>[\[1\]](#deprecated)  
Use `overflow: hidden` instead.

`-moz-scrollbars-horizontal` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>[\[1\]](#deprecated)  
Use `overflow-x`: scroll and `overflow-y`: hidden, or `overflow: hidden scroll` instead.

`-moz-scrollbars-vertical` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>[\[1\]](#deprecated)  
Use `overflow-x`: hidden and `overflow-y`: scroll, or `overflow: scroll hidden` instead.

`-moz-hidden-unscrollable` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Use `overflow: clip` instead.

\[1\] As of Firefox 63, this feature is behind a feature preference setting. In about:config, set `layout.css.overflow.moz-scrollbars.enabled` to `true`

## Description

Overflow options include clipping, showing scrollbars, or displaying the content flowing out of its container into the surrounding area.

Specifying a value other than `visible` (the default) or `clip` creates a new [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context). This is necessary for technical reasons — if a float intersected with the scrolling element it would forcibly rewrap the content after each scroll step, leading to a slow scrolling experience.

In order for `overflow` to have an effect, the block-level container must have either a set height (`height` or `max-height`) or `white-space` set to `nowrap`.

Setting one axis to `visible` (the default) while setting the other to a _different_ value results in `visible` behaving as `auto`.

The JavaScript [`Element.scrollTop`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTop) property may be used to scroll an HTML element even when `overflow` is set to `hidden`.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>visible</code></td></tr><tr class="even"><td>Applies to</td><td>Block-containers, flex containers, and grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="overflow-x"><code>overflow-x</code></a>: as specified, except with <code>visible</code>/<code>clip</code> computing to <code>auto</code>/<code>hidden</code> respectively if one of <a href="overflow-x"><code>overflow-x</code></a> or <a href="overflow-y"><code>overflow-y</code></a> is neither <code>visible</code> nor clip</li><li><a href="overflow-y"><code>overflow-y</code></a>: as specified, except with <code>visible</code>/<code>clip</code> computing to <code>auto</code>/<code>hidden</code> respectively if one of <a href="overflow-x"><code>overflow-x</code></a> or <a href="overflow-y"><code>overflow-y</code></a> is neither <code>visible</code> nor clip</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ visible | hidden | clip | scroll | auto ]{1,2}

## Examples

### Setting different overflow values for text

    p {
      width: 12em;
      height: 6em;
      border: dotted;
      overflow: visible; /* content is not clipped */
    }

`visible` (default)  
Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.

    p { overflow: hidden; /* no scrollbars are provided */ }

`overflow: hidden`  
Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.

    p { overflow: scroll; /* always show scrollbars */ }

`overflow: scroll`  
Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.

    p { overflow: auto; /* append scrollbars if necessary */ }

`overflow: auto`  
Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.

## Specifications

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overflow-3/#propdef-overflow">CSS Overflow Module Level 3<br />
<span class="small">The definition of 'overflow' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td><p>Changed syntax to allow one or two keywords instead of only one</p></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visufx.html#overflow">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'overflow' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`overflow`

1

12

1

After Firefox 3.6, the `overflow` property is correctly applied to table group elements (`<thead>`, `<tbody>`, `<tfoot>`).

4

From version 4 to 6, Internet Explorer enlarges an element with `overflow: visible` (default value) to fit the content inside it. `height` and `width` behave like `min-height` and `min-width`, respectively.

7

1

37

18

4

14

1

1.0

`clip`

90

90

81

1.5-81

No

No

No

90

90

81

4-81

No

No

No

`multiple_keywords`

68

79

61

No

55

No

68

68

61

48

No

10.0

## See also

- Related CSS properties: [`text-overflow`](text-overflow), [`white-space`](white-space), [`overflow-x`](overflow-x), [`overflow-y`](overflow-y), [`overflow-inline`](overflow-inline), [`overflow-block`](overflow-block), [`clip`](clip), [`display`](display)
- [CSS Overflow](css_overflow) and [Debug scrollable overflow](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Debug_Scrollable_Overflow)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overflow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/overflow</a>
