Screen.unlockOrientation()
==========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Screen.unlockOrientation()` method removes all the previous screen locks set by the page/app. The [`ScreenOrientation.unlock()`](../screenorientation/unlock) method should be used instead.

**Note:** This method only works for installed Web apps or for Web pages in [full-screen mode](../fullscreen_api).

Syntax
------

    var unlocked = window.screen.unlockOrientation();

### Return value

Returns `true` if the orientation was successfully unlocked or `false` if the orientation couldn't be unlocked.

Example
-------

    var unlockOrientation = screen.unlockOrientation || screen.mozUnlockOrientation || screen.msUnlockOrientation || (screen.orientation && screen.orientation.unlock);

    if (unlockOrientation()) {
      // orientation was unlocked
    } else {
      // orientation unlock failed
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

See also
--------

-   [`Screen.orientation`](orientation)
-   [`Screen.lockOrientation()`](lockorientation)
-   [`Screen.onorientationchange`](onorientationchange)
-   [Managing screen orientation](../css_object_model/managing_screen_orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen/unlockOrientation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen/unlockOrientation</a>
