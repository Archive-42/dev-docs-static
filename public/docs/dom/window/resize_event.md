Window: resize event
====================

The `resize` event fires when the document view (window) has been resized.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../uievent"><code>UIEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onresize"><code>onresize</code></a></td></tr></tbody></table>

In some earlier browsers it was possible to register `resize` event handlers on any HTML element. It is still possible to set `onresize` attributes or use [`addEventListener()`](../eventtarget/addeventlistener) to set a handler on any element. However, `resize` events are only fired on the [`window`](../window) object (i.e. returned by [`document.defaultView`](../document/defaultview)). Only handlers registered on the `window` object will receive `resize` events.

There is a proposal to allow all elements to be notified of resize changes. See [Resize Observer](https://wicg.github.io/ResizeObserver/) to read the draft document, and [GitHub issues](https://github.com/WICG/ResizeObserver/issues) to read the on-going discussions.

Examples
--------

### Window size logger

The following example reports the window size each time it is resized. Bear in mind that since the example is running in an `<iframe>`, you'll need to actually get the `<iframe>` to resize before you see an effect.

    <p>Resize the browser window to fire the <code>resize</code> event.</p>
    <p>Window height: <span id="height"></span></p>
    <p>Window width: <span id="width"></span></p>

    const heightOutput = document.querySelector('#height');
    const widthOutput = document.querySelector('#width');

    function reportWindowSize() {
      heightOutput.textContent = window.innerHeight;
      widthOutput.textContent = window.innerWidth;
    }

    window.onresize = reportWindowSize;

### addEventListener equivalent

You could set up the event handler using the `addEventListener()` method:

    window.addEventListener('resize', reportWindowSize);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-resize">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'resize' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/cssom-view/#resizing-viewports">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'resize' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`resize_event`

1

Chrome does not emit a `resize` event on page load.

12

Prior to Edge 79, Edge emitted a `resize` event on page load. This is no longer the case.

1

Prior to Firefox 68, Firefox emitted a `resize` event on page load. This is no longer the case.

4

7

Opera does not emit a `resize` event on page load.

1.1

1

Webview does not emit a `resize` event on page load.

18

Chrome does not emit a `resize` event on page load.

4

Prior to Firefox 68, Firefox emitted a `resize` event on page load. This is no longer the case.

10.1

Opera does not emit a `resize` event on page load.

1

1.0

Samsung Internet does not emit a `resize` event on page load.

See also
--------

-   [`GlobalEventHandlers.onresize`](../globaleventhandlers/onresize)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/resize_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/resize_event</a>
