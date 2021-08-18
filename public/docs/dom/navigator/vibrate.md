# Navigator.vibrate()

The `Navigator.vibrate()` method pulses the vibration hardware on the device, if such hardware exists. If the device doesn't support vibration, this method has no effect. If a vibration pattern is already in progress when this method is called, the previous pattern is halted and the new one begins instead.

If the method was unable to vibrate because of invalid parameters, it will return `false`, else it returns `true`. If the pattern leads to a too long vibration, it is truncated: the max length depends on the implementation.

## Syntax

    var successBool = window.navigator.vibrate(pattern);

`pattern`  
Provides a pattern of vibration and pause intervals. Each value indicates a number of milliseconds to vibrate or pause, in alternation. You may provide either a single value (to vibrate once for that many milliseconds) or an array of values to alternately vibrate, pause, then vibrate again. See [Vibration API](../vibration_api) for details.

Passing a value of `0`, an empty array, or an array containing all zeros will cancel any currently ongoing vibration pattern.

## Examples

    window.navigator.vibrate(200); // vibrate for 200ms
    window.navigator.vibrate([100,30,100,30,100,30,200,30,200,30,200,30,100,30,100,30,100]); // Vibrate 'SOS' in Morse.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dev.w3.org/2009/dap/vibration/">Vibration API</a></td><td><span class="spec-rec">Recommendation</span></td><td>Linked to spec is the latest editor's draft; W3C version is a REC.</td></tr></tbody></table>

## Browser compatibility

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

`vibrate`

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

## See also

- [Vibration API](../vibration_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/vibrate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/vibrate</a>
