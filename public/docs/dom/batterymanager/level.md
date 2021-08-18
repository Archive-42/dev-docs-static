# BatteryManager.level

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Indicates the current battery charge level as a value between `0.0` and `1.0`.

## Syntax

    var level = battery.level

On return, `level` is a number representing the system's battery charge level scaled to a value between 0.0 and 1.0. A value of 0 means the `battery`, which is a [`BatteryManager`](../batterymanager) object, is empty and the system is about to be suspended. A value of 1.0 means the battery is full. A value of 1.0 is also returned if the implementation isn't able to determine the battery charge level or if the system is not battery-powered.

## Example

### HTML Content

    <div id="level">(battery level unknown)</div>

### JavaScript Content

    navigator.getBattery().then(function(battery) {

        var level = battery.level;

        document.querySelector('#level').textContent = level;
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/battery/">Battery Status API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`level`

38

79

43-52

No

25

No

38

38

43-52

25

No

3.0

## See also

- [`BatteryManager`](../batterymanager)
- [`Navigator.getBattery`](../navigator/getbattery)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BatteryManager/level" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BatteryManager/level</a>
