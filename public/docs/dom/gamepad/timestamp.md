# Gamepad.timestamp

The `Gamepad.timestamp` property of the [`Gamepad`](../gamepad) interface returns a [`DOMHighResTimeStamp`](../domhighrestimestamp) representing the last time the data for this gamepad was updated.

The idea behind this is to allow developers to determine if the `axes` and `button` data have been updated from the hardware. The value must be relative to the `navigationStart` attribute of the `PerformanceTiming` interface. Values are monotonically increasing, meaning that they can be compared to determine the ordering of updates, as newer values will always be greater than or equal to older values.

**Note**: This property is not currently supported anywhere.

## Syntax

    readonly    attribute DOMHighResTimeStamp timestamp;

## Example

    var gp = navigator.getGamepads()[0];
    console.log(gp.timestamp);

## Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#dom-gamepad-timestamp">Gamepad<br />
<span class="small">The definition of 'Gamepad.timestamp' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`timestamp`

35

21-34

12

29

No

22

15-21

10.1

No

35

25-34

32

22

14-21

10.3

4.0

2.0-3.0

## See also

[Using the Gamepad API](../gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/timestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/timestamp</a>
