# BatteryManager

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `BatteryManager` interface provides ways to get information about the system's battery charge level.

The [`navigator.getBattery()`](navigator/getbattery) method returns a battery promise that is resolved in a `BatteryManager` interface which you can use to interact with the [Battery Status API](battery_status_api).

## Properties

[`BatteryManager.charging`](batterymanager/charging) <span class="badge inline readonly">Read only </span>  
A Boolean value indicating whether or not the battery is currently being charged.

[`BatteryManager.chargingTime`](batterymanager/chargingtime) <span class="badge inline readonly">Read only </span>  
A number representing the remaining time in seconds until the battery is fully charged, or 0 if the battery is already fully charged.

[`BatteryManager.dischargingTime`](batterymanager/dischargingtime) <span class="badge inline readonly">Read only </span>  
A number representing the remaining time in seconds until the battery is completely discharged and the system will suspend.

[`BatteryManager.level`](batterymanager/level) <span class="badge inline readonly">Read only </span>  
A number representing the system's battery charge level scaled to a value between 0.0 and 1.0.

### Event handlers

[`BatteryManager.onchargingchange`](batterymanager/onchargingchange)  
A handler for the `chargingchange` event; This event is sent when the battery charging state is updated.

[`BatteryManager.onchargingtimechange`](batterymanager/onchargingtimechange)  
A handler for the `chargingtimechange` event; This event is sent when the battery charging time is updated

[`BatteryManager.ondischargingtimechange`](batterymanager/ondischargingtimechange)  
A handler for the `dischargingtimechange` event; This event is sent when the battery discharging time is updated.

[`BatteryManager.onlevelchange`](batterymanager/onlevelchange)  
A handler for the `levelchange` event; This event is sent when the battery level is updated.

## Methods

_Inherits methods from its parent interface:_ [`EventTarget`](eventtarget).

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

`BatteryManager`

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

`charging`

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

`dischargingTime`

38

79

43-52

No

25

No

42

38-42

Always equal to `Infinity`.

42

38-42

Always equal to `Infinity`.

43-52

29

25-29

Always equal to `Infinity`.

No

4.0

3.0-4.0

Always equal to `Infinity`.

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

`onchargingchange`

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

`ondischargingtimechange`

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

`onlevelchange`

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

- The [Battery Status API](battery_status_api)
- [`navigator.getBattery`](navigator/getbattery)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BatteryManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BatteryManager</a>
