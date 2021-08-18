Window.clearImmediate()
=======================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

This method clears the action specified by [`window.setImmediate`](setimmediate).

This method is not expected to become standard, and is only implemented by recent builds of Internet Explorer and Node.js 0.10+. It meets resistance both from [Gecko](https://bugzilla.mozilla.org/show_bug.cgi?id=686201) (Firefox) and [Webkit](https://code.google.com/p/chromium/issues/detail?id=146172) (Google/Apple).

Syntax
------

    window.clearImmediate( immediateID )

where immediateID is a ID returned by [`window.setImmediate`](setimmediate).

Examples
--------

    let immediateID = setImmediate(() => {
      // Run some code
    }

    document.getElementById("button")
      .addEventListener(() => {
      clearImmediate(immediateID);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/setImmediate/#si-setImmediate">Efficient Script Yielding<br />
<span class="small">The definition of '<code>setImmediate</code>' in that specification.</span></a></td><td><span class="spec-ED">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`clearImmediate`

No

12-79

No

10

No

No

No

No

No

No

No

No

See also
--------

-   [`Window.setImmediate()`](setimmediate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/clearImmediate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/clearImmediate</a>
