Screen.orientation
==================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `orientation` read-only property of the [`Screen`](../screen) interface returns the current orientation of the screen.

Syntax
------

    var orientation = screen.orientation;

### Return value

An instance of [`ScreenOrientation`](../screenorientation) representing the orientation of the screen.

Note that older, prefixed versions returned a [`DOMString`](../domstring) equivalent to [`ScreenOrientation.type`](../screenorientation/type).

Example
-------

    var orientation = (screen.orientation || {}).type || screen.mozOrientation || screen.msOrientation;

    if (orientation === "landscape-primary") {
      console.log("That looks good.");
    } else if (orientation === "landscape-secondary") {
      console.log("Mmmh... the screen is upside down!");
    } else if (orientation === "portrait-secondary" || orientation === "portrait-primary") {
      console.log("Mmmh... you should rotate your device to landscape");
    } else if (orientation === undefined) {
      console.log("The orientation API isn't supported in this browser :(");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-orientation/#dom-screen-orientation">Screen Orientation API<br />
<span class="small">The definition of 'orientation' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`orientation`

38

79

12

Edge does not return an `Orientation` object; instead, it returns the orientation type as a string.

43

Yes

11

Not supported on Windows 7.

25

No

No

39

43

Yes

No

No

4.0

See also
--------

-   [`ScreenOrientation`](../screenorientation)
-   [`Screen.onorientationchange`](onorientationchange)
-   [Managing screen orientation](../css_object_model/managing_screen_orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen/orientation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen/orientation</a>
