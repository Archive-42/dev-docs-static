# Navigator.maxTouchPoints

The `maxTouchPoints` read-only property of the [`Navigator`](../navigator) interface returns the maximum number of simultaneous touch contact points are supported by the current device.

## Syntax

    touchPoints = navigator.maxTouchPoints;

## Example

    if (navigator.maxTouchPoints > 1) {
      // browser supports multi-touch
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#extensions-to-the-navigator-interface">Pointer Events – Level 2<br />
<span class="small">The definition of 'maxTouchPoints' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#extensions-to-the-navigator-interface">Pointer Events<br />
<span class="small">The definition of 'maxTouchPoints' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`maxTouchPoints`

35

12

59

29

11

10

Yes

13

37

35

79

29

See [bug 1426786](https://bugzil.la/1426786).

Yes

13

3.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/maxTouchPoints" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/maxTouchPoints</a>
