Vibration API
=============

Most modern mobile devices include vibration hardware, which lets software code provide physical feedback to the user by causing the device to shake. The **Vibration API** offers Web apps the ability to access this hardware, if it exists, and does nothing if the device doesn't support it.

Describing vibrations
---------------------

Vibration is described as a pattern of on-off pulses, which may be of varying lengths. The pattern may consist of either a single integer, describing the number of milliseconds to vibrate, or an array of integers describing a pattern of vibrations and pauses. Vibration is controlled with a single method: [`Navigator.vibrate()`](navigator/vibrate).

### A single vibration

You may pulse the vibration hardware one time by specifying either a single value or an array consisting of only one value:

    window.navigator.vibrate(200);
    window.navigator.vibrate([200]);

Both of these examples vibrate the device for 200 ms.

### Vibration patterns

An array of values describes alternating periods in which the device is vibrating and not vibrating. Each value in the array is converted to an integer, then interpreted alternately as the number of milliseconds the device should vibrate and the number of milliseconds it should not be vibrating. For example:

    window.navigator.vibrate([200, 100, 200]);

This vibrates the device for 200 ms, then pauses for 100 ms before vibrating the device again for another 200 ms.

You may specify as many vibration/pause pairs as you like, and you may provide either an even or odd number of entries; it's worth noting that you don't have to provide a pause as your last entry since the vibration automatically stops at the end of each vibration period.

### Canceling existing vibrations

Calling [`Navigator.vibrate()`](navigator/vibrate) with a value of `0`, an empty array, or an array containing all zeros will cancel any currently ongoing vibration pattern.

### Continued vibrations

Some basic `setInterval` and `clearInterval` action will allow you to create persistent vibration:

    var vibrateInterval;

    // Starts vibration at passed in level
    function startVibrate(duration) {
        navigator.vibrate(duration);
    }

    // Stops vibration
    function stopVibrate() {
        // Clear interval and stop persistent vibrating
        if(vibrateInterval) clearInterval(vibrateInterval);
        navigator.vibrate(0);
    }

    // Start persistent vibration at given duration and interval
    // Assumes a number value is given
    function startPersistentVibrate(duration, interval) {
        vibrateInterval = setInterval(function() {
            startVibrate(duration);
        }, interval);
    }

Of course, the snippet above doesn't take into account the array method of vibration; persistent array-based vibration will require calculating the sum of the array items and creating an interval based on that number (with an additional delay, probably).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dev.w3.org/2009/dap/vibration/">Vibration API</a></td><td><span class="spec-rec">Recommendation</span></td><td>Linked to spec is the latest editor's draft; W3C version is a REC.</td></tr></tbody></table>

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

`Vibration_API`

32

79

16

\["Until Firefox 26 included, when the vibration pattern was too long or any of its elements too large, Firefox threw an exception instead of returning `false` ([bug 884935](https://bugzil.la/884935)).", "From Firefox 32 onwards, when the vibration pattern is too long or any of its elements too large, it returns `true` but truncates the pattern ([bug 1014581](https://bugzil.la/1014581)).", "Beginning in Firefox 72, this is not supported in cross-origin iframes."\]

11-true

No

No

No

4.4.3

\["Beginning in version 55, this is not supported in cross-origin iframes.", "Beginning in version 60, this method requires a user gesture. Otherwise it returns `false`."\]

32

\["Beginning in Chrome 55, this is not supported in cross-origin iframes.", "Beginning in Chrome 60, this method requires a user gesture. Otherwise it returns `false`."\]

79

Vibration is disabled. If the window is visible, then `navigator.vibrate()` returns `true`, but no vibration takes place (regardless of hardware support). See [bug 1591113.](https://bugzil.la/1591113)

16-79

\["Until Firefox 26 included, when the vibration pattern was too long or any of its elements too large, Firefox threw an exception instead of returning `false` ([bug 884935](https://bugzil.la/884935)).", "From Firefox 32 onwards, when the vibration pattern is too long or any of its elements too large, it returns `true` but truncates the pattern ([bug 1014581](https://bugzil.la/1014581))."\]

14-true

Yes

Beginning in Opera 47, this method requires a user gesture. Otherwise it returns `false`.

No

2.0

\["Beginning in Samsung Internet 6.0, this is not supported in cross-origin iframes.", "Beginning in Samsung Internet 8.0, this method requires a user gesture. Otherwise it returns `false`."\]

See also
--------

-   [`Navigator.vibrate()`](navigator/vibrate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Vibration_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Vibration_API</a>
