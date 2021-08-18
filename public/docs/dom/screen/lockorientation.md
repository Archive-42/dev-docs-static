Screen.lockOrientation()
========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `lockOrientation()` method of the [`Screen`](../screen) interface locks the screen into a specified orientation. The [`ScreenOrientation.lock()`](../screenorientation/lock) method should be used instead.

**Note:** This method only works for installed Web apps or for Web pages in [full-screen mode](../fullscreen_api).

Syntax
------

    lockAllowed = window.screen.lockOrientation(orientation);

### Parameters

`orientation`  
The orientation into which to lock the screen. This is either a string or an array of strings. Passing several strings lets the screen rotate only in the selected orientations.

The following strings represent the possible orientation requirements you may specify:

`portrait-primary`  
It represents the orientation of the screen when it is in its primary portrait mode. A screen is considered in its primary portrait mode if the device is held in its normal position and that position is in portrait, or if the normal position of the device is in landscape and the device held turned by 90° clockwise. The normal position is device dependant.

`portrait-secondary`  
It represents the orientation of the screen when it is in its secondary portrait mode. A screen is considered in its secondary portrait mode if the device is held 180° from its normal position and that position is in portrait, or if the normal position of the device is in landscape and the device held is turned by 90° counterclockwise. The normal position is device dependant.

`landscape-primary`  
It represents the orientation of the screen when it is in its primary landscape mode. A screen is considered in its primary landscape mode if the device is held in its normal position and that position is in landscape, or if the normal position of the device is in portrait and the device held is turned by 90° clockwise. The normal position is device dependant.

`landscape-secondary`  
It represents the orientation of the screen when it is in its secondary landscape mode. A screen is considered in its secondary landscape mode if the device held is 180° from its normal position and that position is in landscape, or if the normal position of the device is in portrait and the device held is turned by 90° counterclockwise. The normal position is device dependant.

`portrait`  
It represents both `portrait-primary` and `portrait-secondary`.

`landscape`  
It represents both `landscape-primary` and `landscape-secondary`.

`default`  
It represents either `portrait-primary `and `landscape-primary` depends on natural orientation of devices. For example, if the panel resolution is 1280\*800, `default` will make it landscape, if the resolution is 800\*1280, `default` will make it to portrait.

**Note:** It's possible to set several locks at the same time. So, if the lock is set for only one orientation, the screen orientation will never change until the screen orientation is unlocked. Otherwise, the screen orientation will change from an orientation to another as long as the orientations are amongst the orientations the device has been locked to.

### Return value

Returns `true` if the orientation was authorized to be locked or `false` if the orientation locking was denied. Note that the return value doesn't indicate that the screen orientation is indeed locked: there may be a delay.

Examples
--------

### Usage with a `DOMString` argument

    screen.lockOrientationUniversal = screen.lockOrientation || screen.mozLockOrientation || screen.msLockOrientation;

    if (screen.lockOrientationUniversal("landscape-primary")) {
      // Orientation was locked
    } else {
      // Orientation lock failed
    }

### Usage with an `Array` argument

    screen.lockOrientationUniversal = screen.lockOrientation || screen.mozLockOrientation || screen.msLockOrientation;

    if (screen.lockOrientationUniversal(["landscape-primary", "landscape-secondary"])) {
      // Orientation was locked
    } else {
      // Orientation lock failed
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-orientation/published/20140220.html#extensions-to-the-screen-interface">Screen Orientation API<br />
<span class="small">The definition of 'lockOrientation()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition (Not present in the draft anymore)</td></tr></tbody></table>

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

See also
--------

-   [`Screen.orientation`](orientation)
-   [`Screen.unlockOrientation()`](unlockorientation)
-   [`Screen.onorientationchange`](onorientationchange)
-   [Managing screen orientation](../css_object_model/managing_screen_orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen/lockOrientation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen/lockOrientation</a>
