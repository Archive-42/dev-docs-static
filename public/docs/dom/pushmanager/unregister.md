# PushManager.unregister()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `unregister()` method was used to ask the system to unregister and delete the specified endpoint. In the updated API, a subscription is can be unregistered via the [`PushSubscription.unsubscribe()`](../pushsubscription/unsubscribe) method.

## Syntax

    var request = navigator.push.unregister(pushEndpoint);

### Properties

pushEndpoint  
A pushEndpoint to be unregistered.

### Return

A <span class="page-not-created">`DOMRequest`</span> object to handle the success or failure of the method call.

If the method call is successful, the request's `result` will be a [PushRegistration](#pushregistration) object representing the endpoint that has been unregistered.

### PushRegistration

Those objects are anonymous JavaScript objects with the following properties:

`pushEndpoint`  
A string representing the URL of the unregistered endpoint.

`version`  
`Undefined` when `unregister.onsuccess` is called.

## Example

    var req = navigator.push.unregister(pushEndpoint);

    req.onsuccess = function(e) {
      var endpoint = req.result;
      debug("Unregistered endpoint: " + endpoint );
    }

    req.onerror = function(e) {
      debug("Error unregistering the endpoint: " + JSON.stringify(e));
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/">Push API</a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines the <code>PushManager</code> interface.</td></tr></tbody></table>

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

`unregister`

42

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

No

No

42

48

Push enabled by default.

29

No

4.0

## See also

- [`PushManager`](../pushmanager)
- <span class="page-not-created">`DOMRequest`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushManager/unregister" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushManager/unregister</a>
