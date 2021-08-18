# PushManager

The `PushManager` interface of the [Push API](push_api) provides a way to receive notifications from third-party servers as well as request URLs for push notifications.

This interface is accessed via the [`ServiceWorkerRegistration.pushManager`](serviceworkerregistration/pushmanager) property.

**Note**: This interface replaces functionality previously offered by the obsolete [`PushRegistrationManager`](pushregistrationmanager) interface.

## Properties

[`PushManager.supportedContentEncodings`](pushmanager/supportedcontentencodings)  
Returns an array of supported content codings that can be used to encrypt the payload of a push message.

## Methods

[`PushManager.getSubscription()`](pushmanager/getsubscription)  
Retrieves an existing push subscription. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`PushSubscription`](pushsubscription) object containing details of an existing subscription. If no existing subscription exists, this resolves to a `null` value.

[`PushManager.permissionState()`](pushmanager/permissionstate)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the permission state of the current [`PushManager`](pushmanager), which will be one of `'granted'`, `'denied'`, or `'prompt'`.

[`PushManager.subscribe()`](pushmanager/subscribe)  
Subscribes to a push service. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`PushSubscription`](pushsubscription) object containing details of a push subscription. A new push subscription is created if the current service worker does not have an existing subscription.

### Deprecated methods

[`PushManager.hasPermission()`](pushmanager/haspermission) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the `PushPermissionStatus` of the requesting webapp, which will be one of `granted`, `denied`, or `default`. Replaced by [`PushManager.permissionState()`](pushmanager/permissionstate).

[`PushManager.register()`](pushmanager/register) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Subscribes to a push subscription. Replaced by [`PushManager.subscribe()`](pushmanager/subscribe).

[`PushManager.registrations()`](pushmanager/registrations) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Retrieves existing push subscriptions. Replaced by [`PushManager.getSubscription()`](pushmanager/getsubscription).

[`PushManager.unregister()`](pushmanager/unregister) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Unregisters and deletes a specified subscription endpoint. In the updated API, a subscription is unregistered by calling the [`PushSubscription.unsubscribe()`](pushsubscription/unsubscribe) method.

## Example

    this.onpush = function(event) {
      console.log(event.data);
      // From here we can write the data to IndexedDB, send it to any open
      // windows, display a notification, etc.
    }

    navigator.serviceWorker.register('serviceworker.js').then(
      function(serviceWorkerRegistration) {
        serviceWorkerRegistration.pushManager.subscribe().then(
          function(pushSubscription) {
            console.log(pushSubscription.endpoint);
            // The push subscription details needed by the application
            // server are now available, and can be sent to it using,
            // for example, an XMLHttpRequest.
          }, function(error) {
            // During development it often helps to log errors to the
            // console. In a production environment it might make sense to
            // also report information about errors back to the
            // application server.
            console.log(error);
          }
        );
      });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#pushmanager-interface">Push API<br />
<span class="small">The definition of 'PushManager' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PushManager`

42

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

No

No

See [bug 421921](https://crbug.com/421921)

42

48

Push enabled by default.

29

No

4.0

`getSubscription`

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

`hasPermission`

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

`permissionState`

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

`register`

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

`subscribe`

42

The `options` parameter with a `applicationServerKey` value is required.

17

44

\["[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.", "From Firefox 72 onwards, can only be called in response to a user gesture such as a `click` event."\]

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

`supportedContentEncodings`

60

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

47

No

No

60

48

Push enabled by default.

44

No

4.0

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

`worker_support`

42

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers.

No

29

No

No

42

48

29

No

4.0

## See also

- [Push API](push_api)
- [Service Worker API](service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushManager</a>
