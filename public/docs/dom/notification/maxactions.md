# Notification.maxActions

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `maxActions` attribute of the [`Notification`](../notification) interface returns the maximum number of actions supported by the device and the User Agent. Effectively, this is the maximum number of elements in [`Notification.actions`](actions) array which will be respected by the User Agent.

## Syntax

    Notification.maxActions

### Value

An integer [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) which indicates the largest number of notification actions that can be presented to the user by the User Agent and the device.

## Examples

The following snippet logs the maximum number of supported actions.

    const maxActions = Notification.maxActions;
    console.log('This device can display at most ' + maxActions + ' actions on each notification.');

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/">Notifications API</a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`maxActions`

Yes

18

No

No

Yes

No

No

Yes

No

Yes

No

Yes

## See also

- [Using the Notifications API](../notifications_api/using_the_notifications_api)
- [`Notification.actions`](actions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/maxActions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/maxActions</a>
