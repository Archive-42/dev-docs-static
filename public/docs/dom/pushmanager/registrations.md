PushManager.registrations()
===========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `registrations` method is used to ask the system about existing push endpoint registrations.

Syntax
------

    var request = navigator.push.registrations();

### Return

A <span class="page-not-created">`DOMRequest`</span> object to handle the success or failure of the method call.

If the method call is successful, the request's `result` will be an array of [PushRegistration](#pushregistration) objects.

### PushRegistration

Those objects are anonymous JavaScript objects with the following properties:

`pushEndpoint`  
A string representing the URL of the endpoint.

`version`  
The current version that the push endpoint is at.

Example
-------

    var req = navigator.push.registrations();

    req.onsuccess = function(e) {
      if (req.result.length > 0) {
        for (var i = 0, l = req.result.length; i < l; i++) {
          console.log("Existing registration", req.result[i].pushEndpoint, req.result[i].version);
        }
        // Reuse existing endpoints.
      } else {
        // Register for a new endpoint.
        var register = navigator.push.register();
        register.onsuccess = function(e) {
          console.log("Registered new endpoint", register.result);
        }
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/">Push API</a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines the <code>PushManager</code> interface.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`registrations`

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

See also
--------

-   [`PushManager`](../pushmanager)
-   <span class="page-not-created">`DOMRequest`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushManager/registrations" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushManager/registrations</a>
