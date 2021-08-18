# PaymentRequestEvent.openWindow()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `openWindow` property of the [`PaymentRequestEvent`](../paymentrequestevent) interface opens the specified URL in a new window, if and only if the given URL is on the same origin as the calling page. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a reference to a [`WindowClient`](../windowclient).

## Syntax

    var aPromise = paymentRequestEvent.openWindow(url)

### Parameters

url  
The URL to open in the new window. It must be on the same origin as the calling page.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a reference to a [`WindowClient`](../windowclient).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-handler/#openwindow-method">Payment Handler API<br />
<span class="small">The definition of 'openWindow' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`openWindow`

70

79

No

No

57

No

No

70

No

49

No

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent/openWindow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent/openWindow</a>
