# PushSubscriptionOptions

The `PushSubscriptionOptions` interface of the [Push API](push_api) represents the options associated with a push subscription.

The read-only `PushSubscriptionOptions` object is returned by calling [`PushSubscription.options`](pushsubscription/options) on a [`PushSubscription`](pushsubscription). This interface has no constructor of its own.

## Properties

[`PushSubscriptionOptions.userVisibleOnly`](pushsubscriptionoptions/uservisibleonly)<span class="badge inline readonly">Read only </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating that the returned push subscription will only be used for messages whose effect is made visible to the user.

[`PushSubscriptionOptions.applicationServerKey`](pushsubscriptionoptions/applicationserverkey)<span class="badge inline readonly">Read only </span>  
A public key your push server will use to send messages to client apps via a push server.

## Examples

Calling [`PushSubscription.options`](pushsubscription/options) on a [`PushSubscription`](pushsubscription) returns a `PushSubscriptionOptions` object. In the example below this is printed to the console.

    navigator.serviceWorker.ready.then(function(reg) {
      reg.pushManager.getSubscription().then(function(subscription) {
        let options = subscription.options;
        console.log(options); // a PushSubscriptionOptions object
      })
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-pushsubscriptionoptions">Push API<br />
<span class="small">The definition of 'PushSubscriptionOptions' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PushSubscriptionOptions`

Yes

≤18

Yes

No

Yes

No

No

See [bug 421921](https://crbug.com/421921)

Yes

Yes

Yes

No

Yes

`applicationServerKey`

Yes

17

Yes

No

Yes

No

No

Yes

Yes

Yes

No

Yes

`userVisibleOnly`

Yes

17

?

No

Yes

No

No

Yes

?

Yes

No

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushSubscriptionOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushSubscriptionOptions</a>
