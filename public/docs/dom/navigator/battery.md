# Navigator.battery

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `battery` read-only property returns a [`BatteryManager`](../batterymanager) which provides information about the system's battery charge level and whether the device is charging and exposes events that fire when these parameters change. This interface was introduced in early drafts of the [Battery Status API](../battery_status_api) and but has been replaced with [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-based [`Navigator.getBattery()`](getbattery).

The `battery` property has been removed in favor of the standard [`Navigator.getBattery()`](getbattery) method, which returns a battery [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Syntax

    var battery = navigator.battery;

## Browser compatibility

No compatibility data found for `api.Navigator.battery`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [`Navigator.getBattery()`](getbattery)
- [Battery Status API](../battery_status_api)
- [Blog post - Using the Battery API](https://hacks.mozilla.org/2012/02/using-the-battery-api-part-of-webapi/)
- [David Walsh on the JavaScript Battery API](https://davidwalsh.name/battery-api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/battery" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/battery</a>
