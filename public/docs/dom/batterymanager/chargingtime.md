# BatteryManager.chargingTime

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Indicates the amount of time, in seconds, that remain until the battery is fully charged.

Even if the time returned is precise to the second, browsers round them to a higher interval (typically to the closest 15 minutes) for privacy reasons.

## Syntax

    var time = battery.chargingTime

On return, `time` is the remaining time in seconds until the `battery`, which is a [`BatteryManager`](../batterymanager) object, is fully charged, or 0 if the battery is already fully charged. If the battery is currently discharging, this value is `Infinity`.

## Example

### HTML Content

    <div id="chargingTime">(charging time unknown)</div>

### JavaScript Content

    navigator.getBattery().then(function(battery) {

       var time = battery.chargingTime;

       document.querySelector('#chargingTime').textContent = battery.chargingTime;
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

`chargingTime`

38

79

43-52

No

25

No

42

38-42

Always equal to `0` or `Infinity`.

42

38-42

Always equal to `0` or `Infinity`.

43-52

29

25-29

Always equal to `0` or `Infinity`.

No

4.0

3.0-4.0

Always equal to `0` or `Infinity`.

## See also

- [`BatteryManager`](../batterymanager)
- [`Navigator.getBattery`](../navigator/getbattery)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BatteryManager/chargingTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BatteryManager/chargingTime</a>
