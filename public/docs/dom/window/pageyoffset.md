Window.pageYOffset
==================

The read-only [`Window`](../window) property `pageYOffset` is an alias for [`scrollY`](scrolly); as such, it returns the number of pixels the document is currently scrolled along the vertical axis (that is, up or down) with a value of 0.0, indicating that the top edge of the [`Document`](../document) is currently aligned with the top edge of the window's content area.

There is slightly better support for `pageYOffset` than for `scrollY` in older browsers, but if you're not concerned about browsers more than a handful of years old, you can use either one.

The corresponding [`pageXOffset`](pagexoffset) property, which returns the number of pixels scrolled along the horizontal axis (left and right), is an alias for [`scrollX`](scrollx).

Syntax
------

    yOffset = window.pageYOffset;

### Value

A floating-point number specifying the number of pixels the [`Document`](../document) is scrolled vertically within its containing [`Window`](../window). This number is subpixel precise, so it may not be an integer. A value of 0.0 indicates that the window is not scrolled vertically, and that the top of the document is located at the top edge of the window's content area.

Since this property is an alias for [`Window.scrollY`](scrolly), see that article for additional details on this value and its use.

Example
-------

In this example, an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) is created and filled with content, then a specific element within the document is scrolled into view in the frame. Once that's done, the vertical scroll position is checked by looking at the value of `pageYOffset` in the frame's [`contentWindow`](../htmliframeelement/contentwindow).

### HTML

The HTML is extremely simple and has just two elements: an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) that contains the document we're going to scroll, and a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) into which we'll output the value of `pageYOffset` when we've finished the scroll.

    <iframe id="frame">
    </iframe>

    <div id="info">
    </div>

### JavaScript

    var frame = document.getElementById("frame");
    var frameDoc = frame.contentDocument;
    var info = document.getElementById("info");

    var target = frameDoc.getElementById("overview");
    frameDoc.scrollingElement.scrollTop = target.offsetTop;

    info.innerText = "Y offset after scrolling: " +
                     frame.contentWindow.pageYOffset + " pixels";

The JavaScript code begins by getting into `frame` and `info` the `<iframe>` element that contains our content as well as the `<div>` element into which we'll output the result of our scroll position check. It then gets a reference to the element we want to scroll into view calling [`getElementById()`](../document/getelementbyid) on the frame's [`HTMLIFrameElement.contentDocument`](../htmliframeelement/contentdocument).

With the target element in hand, we set the [`scrollTop`](../element/scrolltop) of the frame's [`scrollingElement`](../document/scrollingelement) to the <span class="page-not-created">`offsetTop`</span> of the target element. By doing so, we set the vertical scrolling position of the frame's document so that it's the same as the top edge of the target element.

This will automatically set the scrolling position to the maximum possible value if the attempted scroll would exceed the maximum. This prevents us from falling off the edge of the document. Nobody wants to know what's out there. There might be dragons.

### Result

The result follows. Note that the frame's contents have been scrolled to show the section named "Overview", and that the value of the `pageYOffset` property is shown with the corresponding value.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-pageyoffset">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'window.pageYOffset' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`pageYOffset`

1

12

1

9

3

1

1

18

4

10.1

1

1.0

See also
--------

-   [`pageXOffset`](pagexoffset)
-   [`scrollY`](scrolly) and [`scrollX`](scrollx)
-   [`scroll()`](scroll), [`scrollBy()`](scrollby), and [`scrollTo()`](scrollto)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/pageYOffset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/pageYOffset</a>
