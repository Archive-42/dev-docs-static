Screen
======

The `Screen` interface represents a screen, usually the one on which the current window is being rendered, and is obtained using [`window.screen`](window/screen).

Note that browsers determine which screen to report as current by detecting which screen has the center of the browser window.

Properties
----------

 [`Screen.availTop`](screen/availtop) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Specifies the y-coordinate of the first pixel that is not allocated to permanent or semipermanent user interface features.

 [`Screen.availLeft`](screen/availleft) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the first available pixel available from the left side of the screen.

[`Screen.availHeight`](screen/availheight)  
Specifies the height of the screen, in pixels, minus permanent or semipermanent user interface features displayed by the operating system, such as the Taskbar on Windows.

[`Screen.availWidth`](screen/availwidth)  
Returns the amount of horizontal space in pixels available to the window.

[`Screen.colorDepth`](screen/colordepth)  
Returns the color depth of the screen.

[`Screen.height`](screen/height)  
Returns the height of the screen in pixels.

 [`Screen.left`](screen/left) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the distance in pixels from the left side of the main screen to the left side of the current screen.

[`Screen.orientation`](screen/orientation)  
Returns the [`ScreenOrientation`](screenorientation) instance associated with this screen.

[`Screen.pixelDepth`](screen/pixeldepth)  
Gets the bit depth of the screen.

 [`Screen.top`](screen/top) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the distance in pixels from the top side of the current screen.

[`Screen.width`](screen/width)  
Returns the width of the screen.

 [`Screen.mozEnabled`](screen/mozenabled) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Boolean. Setting to false will turn off the device's screen.

 [`Screen.mozBrightness`](screen/mozbrightness) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Controls the brightness of a device's screen. A double between 0 and 1.0 is expected.

### Events handler

 [`Screen.onorientationchange`](screen/onorientationchange) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A handler for the `orientationchange` event.

Methods
-------

[`Screen.lockOrientation`](screen/lockorientation)  
Lock the screen orientation (only works in fullscreen or for installed apps)

[`Screen.unlockOrientation`](screen/unlockorientation)  
Unlock the screen orientation (only works in fullscreen or for installed apps)

*Methods inherited from [`EventTarget`](eventtarget):*

[`EventTarget.addEventListener()`](eventtarget/addeventlistener)  
Registers an event handler of a specific event type on the `EventTarget`.

[`EventTarget.removeEventListener()`](eventtarget/removeeventlistener)  
Removes an event listener from the `EventTarget`.

[`EventTarget.dispatchEvent()`](eventtarget/dispatchevent)  
Dispatches an event to this `EventTarget`.

Example
-------

    if (screen.pixelDepth < 8) {
      // use low-color version of page
    } else {
      // use regular, colorful page
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#the-screen-interface">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Screen' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Screen`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`availHeight`

1

12

Always reflects the main screen.

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`availLeft`

1

79

1

No

15

1

1

18

4

14

1

1.0

`availTop`

1

79

1

No

15

1

1

18

4

14

1

1.0

`availWidth`

1

12

Always reflects the main screen.

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`colorDepth`

1

Starting with version 59 this property is no longer required to always return 24.

12

1

4

≤12.1

1

1

Starting with version 59 this property is no longer required to always return 24.

18

Starting with version 59 this property is no longer required to always return 24.

4

≤12.1

1

1.0

Starting with Samsung Internet 7.0 this property is no longer required to always return 24.

`height`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`left`

No

≤18-79

1

No

No

Yes

No

No

4

No

?

No

`lockOrientation`

38

12

Yes

11

Yes

No

38

38

Yes

Yes

No

3.0

`mozBrightness`

No

No

12

No

No

No

No

No

14

No

No

No

`mozEnabled`

No

No

12

No

No

No

No

No

14

No

No

No

`onorientationchange`

No

≤18-79

No

No

No

No

No

No

Yes

No

No

No

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

`pixelDepth`

1

Starting with version 59 this property is no longer required to always return 24.

12

1

9

≤12.1

1

1

Starting with version 59 this property is no longer required to always return 24.

18

Starting with version 59 this property is no longer required to always return 24.

4

≤12.1

1

1.0

Starting with Samsung Internet 7.0 this property is no longer required to always return 24.

`top`

No

≤18-79

1

No

No

Yes

No

No

4

No

?

No

`unlockOrientation`

38

12

Yes

11

Yes

No

38

38

Yes

Yes

No

3.0

`width`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen</a>
