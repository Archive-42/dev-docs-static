# PushSubscription

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PushSubscription` interface of the [Push API](push_api) provides a subcription's URL endpoint and allows unsubscription from a push service.

An instance of this interface can be serialized.

## Properties

[`PushSubscription.endpoint`](pushsubscription/endpoint) <span class="badge inline readonly">Read only </span>  
A [`USVString`](usvstring) containing the endpoint associated with the push subscription.

[`PushSubscription.expirationTime`](pushsubscription/expirationtime) <span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) of the subscription expiration time associated with the push subscription, if there is one, or null otherwise.

[`PushSubscription.options`](pushsubscription/options) <span class="badge inline readonly">Read only </span>  
An object containing the options used to create the subscription.

[`PushSubscription.subscriptionId`](pushsubscription/subscriptionid) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) containing the subscription ID associated with the push subscription.

## Methods

[`PushSubscription.getKey()`](pushsubscription/getkey)  
Returns an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) which contains the client's public key, which can then be sent to a server and used in encrypting push message data.

[`PushSubscription.toJSON()`](pushsubscription/tojson)  
Standard serializer — returns a JSON representation of the subscription properties.

[`PushSubscription.unsubscribe()`](pushsubscription/unsubscribe)  
Starts the asynchronous process of unsubscribing from the push service, returning a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) when the current subscription is successfully unregistered.

## Example

    navigator.serviceWorker.ready.then(function(reg) {
      reg.pushManager.getSubscription().then(function(subscription) {
        subscription.unsubscribe().then(function(successful) {
          // You've successfully unsubscribed
        }).catch(function(e) {
          // Unsubscription failed
        })
      })
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#pushsubscription-interface">Push API<br />
<span class="small">The definition of 'PushSubscription' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`PushSubscription`

42

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

No

No

See [bug 421921](https://crbug.com/421921)

42

48

29

No

4.0

`endpoint`

42

16

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

No

No

42

48

29

No

4.0

`expirationTime`

60

16

No

No

47

No

No

60

No

44

No

8.0

`getKey`

42

16

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

No

No

42

48

29

No

4.0

`options`

42

16

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

No

No

42

48

29

No

4.0

`subscriptionId`

42

≤18

No

No

29

No

No

42

No

29

No

4.0

`toJSON`

42

17

46

No

Yes

No

No

50

48

Yes

No

5.0

`unsubscribe`

42

16

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

Yes

No

No

50

48

Yes

No

5.0

## See also

- [Push API](push_api)
- [Service Worker API](service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription</a>
