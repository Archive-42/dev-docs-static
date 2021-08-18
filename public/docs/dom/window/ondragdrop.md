Window.ondragdrop
=================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Removed in Firefox 50, and never implemented in any other browser. Use the modern standard [HTML5 drag and drop](../html_drag_and_drop_api) feature instead.

Summary
-------

An event handler for drag and drop events sent to the window.

Syntax
------

    window.ondragdrop = funcRef;
    window.addEventListener("dragdrop", funcRef, useCapturing);

funcRef   
The event handler function to be registered.

The `window.ondragdrop` property and the `ondragdrop` attribute are not implemented in [Gecko](https://developer.mozilla.org/en-US/Gecko) ([bug 112288](https://bugzilla.mozilla.org/show_bug.cgi?id=112288)), you have to use `addEventListener`. See [addEventListener](../eventtarget/addeventlistener) for details.

Example
-------

### Fire an alert on dragdrop

In this example, an event listener is added to the window (the event target). If, from an external source, a tab, a link, marked text or a file is dragged and dropped onto this window, the alert is fired. Note how `event.stopPropagation();` prevents the browser from loading the dropped tab, link or file.

    <html>
    <head><title>dragdroptest</title>

    <script type="text/javascript">

    window.addEventListener("dragdrop", testfunc, false);

    function testfunc(event) {
        alert("dragdrop!");
        event.stopPropagation();
    }
    </script>

    </head>
    <body>
    I am bodytext
    </body>
    </html>

<span class="external">Specification </span>
--------------------------------------------

<span class="external">Not part of specification. </span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/ondragdrop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/ondragdrop</a>
