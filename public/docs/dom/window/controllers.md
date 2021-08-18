Window.controllers
==================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `controllers` property of the [`Window`](../window) interface returns the XUL controllers of the chrome window.

Syntax
------

    controllers = window.controllers

-   `controllers` is an object of type [`XULControllers`](https://developer.mozilla.org/en-US/docs/XULControllers) ([`nsIControllers`](https://developer.mozilla.org/en-US/docs/XPCOM_Interface_Reference/nsIControllers)).

Specifications
--------------

XUL-specific. Not part of specification.

By default, a window's controller contains the code that supports the global window commands.

Chrome code can add controllers (to be used in conjunction with the `goDoCommand` and `goUpdateCommand` functions in globalOverlay.js).

However, the added controllers must be explicitly removed when the window is unloaded, as this is not done automatically.

Each missing removal can cause

[bug 415775](https://bugzilla.mozilla.org/show_bug.cgi?id=415775):

    ASSERTION: XPConnect is being called on a scope without a 'Components' property!

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/controllers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/controllers</a>
