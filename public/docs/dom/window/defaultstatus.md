Window.defaultStatus
====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:**This method was removed from Firefox 23 and onward.

Summary
-------

Gets/sets the status bar text for the given window.

Syntax
------

    var sMsg = window.defaultStatus;
    window.defaultStatus = sMsg;

### Parameters

-   `sMsg` is a string containing the text to be displayed by default in the statusbar.

Example
-------

    <html>
     <body onload="window.defaultStatus='hello!';"/>
      <button onclick="window.confirm('Are you sure you want to quit?');">confirm</button>
     </body>
    </html>

Notes
-----

To set the status once the window has been opened, use [`window.status`](status).

Specifications
--------------

HTML5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/defaultStatus" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/defaultStatus</a>
