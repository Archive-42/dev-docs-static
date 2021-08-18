Window.onappinstalled
=====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `onappinstalled` attribute of the [`Window`](../window) object serves as an event handler for the `appinstalled` event, which is dispatched once the web application is successfully installed as a [progressive web app](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps). The event that is fired is a "simple event" that implements the [`Event`](../event) interface.

Syntax
------

    window.onappinstalled = function(event) { ... };

Example
-------

    window.onappinstalled = function(ev) {
      console.log('The application was installed.');
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

`onappinstalled`

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

-   [`Event`](../event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/onappinstalled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/onappinstalled</a>
