Window.updateCommands()
=======================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Summary
-------

Updates the state of commands of the current chrome window (UI).

Syntax
------

    window.updateCommands("sCommandName")

Parameters
----------

-   `sCommandName` is a particular string which describes what kind of update event this is (e.g. whether we are in bold right now).

Notes
-----

This enables or disables items (setting or clearing the "disabled" attribute on the command node as appropriate), or ensures that the command state reflects the state of the selection by setting current state information in the "state" attribute of the XUL command nodes.

Specifications
--------------

DOM Level 0. Not part of specification.

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

`updateCommands`

No

No

1

No

?

No

No

No

4

?

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/updateCommands" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/updateCommands</a>
