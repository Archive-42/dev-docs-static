ScreenOrientation
=================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ScreenOrientation` interface of the [Screen Orientation API](screen_orientation_api) provides information about the current orientation of the document.

A `ScreenOrientation` instance object can be retrieved using the [`screen.orientation`](screen/orientation) property.

Properties
----------

 [`ScreenOrientation.type`](screenorientation/type)<span class="badge inline readonly">Read only </span>   
Returns the document's current orientation type, one of "portrait-primary", "portrait-secondary", "landscape-primary", or "landscape-secondary".

 [`ScreenOrientation.angle`](screenorientation/angle)<span class="badge inline readonly">Read only </span>   
Returns the document's current orientation angle.

### Event handlers

[`ScreenOrientation.onchange`](screenorientation/onchange)  
The [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called whenever the screen changes orientation.

Methods
-------

[`ScreenOrientation.lock()`](screenorientation/lock)  
Locks the orientation of the containing document to its default orientation and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

[`ScreenOrientation.unlock()`](screenorientation/unlock)  
Unlocks the orientation of the containing document from its default orientation.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-orientation/#screenorientation-interface">Screen Orientation API<br />
<span class="small">The definition of 'ScreenOrientation' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ScreenOrientation`

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

`angle`

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

`onchange`

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

`type`

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

`unlock`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ScreenOrientation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ScreenOrientation</a>
