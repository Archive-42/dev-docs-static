# HTMLElement.offsetLeft

The `HTMLElement.offsetLeft` read-only property returns the number of pixels that the _upper left corner_ of the current element is offset to the left within the [`HTMLElement.offsetParent`](offsetparent) node.

For block-level elements, `offsetTop`, `offsetLeft`, `offsetWidth`, and `offsetHeight` describe the border box of an element relative to the `offsetParent`.

However, for inline-level elements (such as **span**) that can wrap from one line to the next, `offsetTop` and `offsetLeft` describe the positions of the _first_ border box (use [`Element.getClientRects()`](../element/getclientrects) to get its width and height), while `offsetWidth` and `offsetHeight` describe the dimensions of the _bounding_ border box (use [`Element.getBoundingClientRect()`](../element/getboundingclientrect) to get its position). Therefore, a box with the left, top, width and height of `offsetLeft`, `offsetTop`, `offsetWidth` and `offsetHeight` will not be a bounding box for a span with wrapped text.

## Syntax

    left = element.offsetLeft;

`left` is an integer representing the offset to the left in pixels _from the closest relatively positioned_ parent element.

## Example

    var colorTable = document.getElementById("t1");
    var tOLeft = colorTable.offsetLeft;

    if (tOLeft > 5) {
      // large left offset: do something here
    }

This example shows a 'long' sentence that wraps within a div with a blue border, and a red box that one might think should describe the boundaries of the span.

<img src="data:image/jpeg;base64,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" width="531" height="78" />

    <div style="width: 300px; border-color:blue; border-style:solid; border-width:1;">
      <span>Short span. </span>
      <span id="longspan">Long span that wraps within this div.</span>
    </div>

    <div id="box" style="position: absolute; border-color: red; border-width: 1; border-style: solid; z-index: 10">
    </div>

    <script type="text/javascript">
      var box = document.getElementById("box");
      var longspan = document.getElementById("longspan");
      box.style.left = longspan.offsetLeft + document.body.scrollLeft + "px";
      box.style.top = longspan.offsetTop + document.body.scrollTop + "px";
      box.style.width = longspan.offsetWidth + "px";
      box.style.height = longspan.offsetHeight + "px";
    </script>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-htmlelement-offsetleft">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'offsetLeft' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`offsetLeft`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

## See also

- [`HTMLElement.offsetParent`](offsetparent), [`HTMLElement.offsetTop`](offsettop), [`HTMLElement.offsetWidth`](offsetwidth), [`HTMLElement.offsetHeight`](offsetheight)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetLeft" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetLeft</a>
