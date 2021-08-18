# Battery Status API

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The **Battery Status API**, more often referred to as the **Battery API**, provides information about the system's battery charge level and lets you be notified by events that are sent when the battery level or charging status change. This can be used to adjust your app's resource usage to reduce battery drain when the battery is low, or to save changes before the battery runs out in order to prevent data loss.

**Note:** This API is _not available_ in [Web Workers](web_workers_api) (not exposed via [`WorkerNavigator`](workernavigator)).

The Battery Status API extends [`window.navigator`](window/navigator) with a [`navigator.getBattery()`](navigator/getbattery) method returning a battery promise, which is resolved in a [`BatteryManager`](batterymanager) object providing also some new events you can handle to monitor the battery status.

## Example

In this example, we watch for changes both to the charging status (whether or not we're plugged in and charging) and for changes to the battery level and timing. This is done by listening for the `chargingchange`, `levelchange`, `chargingtimechange`, `dischargingtimechange` events.

    navigator.getBattery().then(function(battery) {
      function updateAllBatteryInfo(){
        updateChargeInfo();
        updateLevelInfo();
        updateChargingInfo();
        updateDischargingInfo();
      }
      updateAllBatteryInfo();

      battery.addEventListener('chargingchange', function(){
        updateChargeInfo();
      });
      function updateChargeInfo(){
        console.log("Battery charging? "
                    + (battery.charging ? "Yes" : "No"));
      }

      battery.addEventListener('levelchange', function(){
        updateLevelInfo();
      });
      function updateLevelInfo(){
        console.log("Battery level: "
                    + battery.level * 100 + "%");
      }

      battery.addEventListener('chargingtimechange', function(){
        updateChargingInfo();
      });
      function updateChargingInfo(){
        console.log("Battery charging time: "
                     + battery.chargingTime + " seconds");
      }

      battery.addEventListener('dischargingtimechange', function(){
        updateDischargingInfo();
      });
      function updateDischargingInfo(){
        console.log("Battery discharging time: "
                     + battery.dischargingTime + " seconds");
      }

    });

See also [the example in the specification](https://www.w3.org/TR/battery-status/#examples).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/battery/">Battery Status API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Battery_Status_API`

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

- [Retrieving battery status information - demo & article](https://developer.mozilla.org/en-US/docs/Web/Apps/Build/gather_and_modify_data/retrieving_battery_status_information)
- [Hacks blog post - Using the Battery API](https://hacks.mozilla.org/2012/02/using-the-battery-api-part-of-webapi/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Battery_Status_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Battery_Status_API</a>
