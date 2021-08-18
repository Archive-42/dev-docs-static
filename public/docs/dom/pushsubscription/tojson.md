# PushSubscription.toJSON()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `toJSON()` method of the [`PushSubscription`](../pushsubscription) interface is a standard serializer: it returns a JSON representation of the subscription properties, providing a useful shortcut.

## Syntax

    mySubscription = subscription.toJSON()

### Parameters

None.

### Returns

A JSON object. It currently only contains the subscription endpoint, as an `endpoint` member.

## Example

    navigator.serviceWorker.ready.then(function(reg) {
      reg.pushManager.getSubscription().then(function(subscription) {
        var mySubscription = subscription.toJSON();
        // do something with subscription details
      })
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-pushsubscription-tojson">Push API<br />
<span class="small">The definition of 'PushSubscription: toJSON' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription/toJSON</a>
