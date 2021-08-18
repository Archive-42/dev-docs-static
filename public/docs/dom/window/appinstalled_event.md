Window: appinstalled event
==========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `appinstalled` event of the [Web Manifest API](https://developer.mozilla.org/en-US/docs/Web/Manifest) is fired when the browser has successfully installed a page as an application.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler</td><td><a href="onappinstalled"><code>onappinstalled</code></a></td></tr></tbody></table>

Examples
--------

You can use the `appinstalled` event in an [`addEventListener`](../eventtarget/addeventlistener) method:

    window.addEventListener('appinstalled', function() {
      console.log('Thank you for installing our app!');
    });

Or use the [`onappinstalled`](onappinstalled) event handler property:

    window.onappinstalled = function() {
      console.log('Thank you for installing our app!');
    };

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

`appinstalled_event`

64

≤79

49-76

No

No

No

57

57

49

No

No

7.0

See also
--------

-   The associated event handler, [`Window.onappinstalled`](onappinstalled)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/appinstalled_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/appinstalled_event</a>
