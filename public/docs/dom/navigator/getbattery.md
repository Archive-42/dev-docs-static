# Navigator.getBattery()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `getBattery()` method provides information about the system's battery. It returns a battery promise, which is resolved in a [`BatteryManager`](../batterymanager) object providing also some new events you can handle to monitor the battery status. This implements the [Battery Status API](../battery_status_api); see that documentation for additional details, a guide to using the API, and sample code.

**Note:** In some browsers access to this feature is controlled by [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) directive [`battery`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/battery).

## Syntax

    var batteryPromise = navigator.getBattery();

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which, when resolved, calls its fulfillment handler with a single parameter: a [`BatteryManager`](../batterymanager) object which you can use to get information about the battery's state.

## Exceptions

This method doesn't throw true exceptions; instead, it rejects the returned promise, passing into it a [`DOMException`](../domexception) whose `name` is one of the following:

`SecurityError`  
The User Agent does not expose battery information to insecure contexts and this method was called from insecure context.  
**Note:** Old versions of some User Agents might allow use of this feature in insecure contexts.

`NotAllowedError`  
**Note:** No User Agent currently throws this exception, but the specification describes the following behaviors:  
This document is not allowed to use this feature. For example, it might not be explicitly allowed or restricted via [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) [`battery`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/battery) feature.

## Example

This example fetches the current charging state of the battery and establishes a handler for the `chargingchange` event, so that the charging state is recorded whenever it changes.

    let batteryIsCharging = false;

    navigator.getBattery().then(function(battery) {
      batteryIsCharging = battery.charging;

      battery.addEventListener('chargingchange', function() {
        batteryIsCharging = battery.charging;
      });
    });

For more examples and details, see [Battery Status API](../battery_status_api).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/battery/#dom-navigator-getbattery">Battery Status API<br />
<span class="small">The definition of 'Navigator.getBattery()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`getBattery`

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

- [Battery Status API](../battery_status_api)
- `Feature-Policy` [`battery`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/battery) feature

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getBattery" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getBattery</a>
