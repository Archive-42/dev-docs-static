ScreenOrientation.lock()
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `lock()` property of the [`ScreenOrientation`](../screenorientation) interface locks the orientation of the containing document to its default orientation.

Syntax
------

    screen.orientation.lock(orientation)

### Parameters

orientation  
An orientation lock type. One of the following:

-   `"any"`
-   `"natural"`
-   `"landscape"`
-   `"portrait"`
-   `"portrait-primary"`
-   `"portrait-secondary"`
-   `"landscape-primary"`
-   `"landscape-secondary"`

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-orientation/#dom-screenorientation-lock">Screen Orientation API<br />
<span class="small">The definition of 'lock()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`lock`

38

79

43

No

25

No

38

38

43

25

No

3.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ScreenOrientation/lock" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ScreenOrientation/lock</a>
