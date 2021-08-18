# BatteryManager.onchargingtimechange

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Specifies an event listener to receive `chargingtimechange` events. These events occur when the battery [`chargingTime`](chargingtime) is updated.

## Syntax

    battery.onchargingtimechange = funcRef

Where `battery` is a [`BatteryManager`](../batterymanager) object, and `funcRef` is a function to be called when the `chargingtimechange` event occurs.

## Example

### HTML Content

    <div id="level">(battery level unknown)</div>
    <div id="chargingTime">(charging time unknown)</div>

### JavaScript Content

    navigator.getBattery().then(function(battery) {

        battery.onchargingtimechange = chargingTimeChange();

        function chargingTimeChange(){
            document.querySelector('#level').textContent = battery.level;
            document.querySelector('#chargingTime').textContent = battery.chargingTime;
        }

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

`onchargingtimechange`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BatteryManager/onchargingtimechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BatteryManager/onchargingtimechange</a>
