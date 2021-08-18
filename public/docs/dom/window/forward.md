Window.forward()
================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Moves the window one document forward in history. This was a Firefox-specific method and was removed in Firefox 31.

**Note:** Use the standard [`window.history.forward()`](../history/forward) method instead.

Syntax
------

    window.forward();

### Parameters

None

### Return value

`undefined`.

Example
-------

    function goForward() {
      if (canGoForward) {
        window.forward();
      }
    }

Specifications
--------------

This is not part of any specification.

Browser compatibility
---------------------

See also
--------

-   [`History.back()`](../history/back)
-   [`History.forward()`](../history/forward)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/forward" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/forward</a>
