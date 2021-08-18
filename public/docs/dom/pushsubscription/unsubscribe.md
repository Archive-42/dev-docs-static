# PushSubscription.unsubscribe()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `unsubscribe()` method of the [`PushSubscription`](../pushsubscription) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) when the current subscription is successfully unsubscribed.

## Syntax

    PushSubscription.unsubscribe().then(function(Boolean) { ... });

### Parameters

None.

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) when the current subscription is successfully unsubscribed.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-pushsubscription-unsubscribe">Push API<br />
<span class="small">The definition of 'unsubscribe()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

- [`PushManager.getSubscription`](../pushmanager/getsubscription)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription/unsubscribe" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription/unsubscribe</a>
