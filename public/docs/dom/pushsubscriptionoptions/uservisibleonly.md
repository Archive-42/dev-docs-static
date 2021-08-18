# PushSubscriptionOptions.userVisibleOnly

The `userVisibleOnly` read-only property of the [`PushSubscriptionOptions`](../pushsubscriptionoptions) interface indicates if the returned push subscription will only be used for messages whose effect is made visible to the user.

## Syntax

    let userVisibleOnly = PushSubscriptionOptions.userVisibleOnly;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the returned push subscription will only be used for messages whose effect is made visible to the user.

## Examples

In the example below the value of `userVisibleOnly` is printed to the console.

    navigator.serviceWorker.ready.then(function(reg) {
      reg.pushManager.getSubscription().then(function(subscription) {
        let options = subscription.options;
        console.log(options.userVisibleOnly); // true if this is a user visible subscription
      })
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-pushsubscriptionoptions-uservisibleonly">Push API<br />
<span class="small">The definition of 'PushSubscriptionOptions.userVisibleOnly' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushSubscriptionOptions/userVisibleOnly" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushSubscriptionOptions/userVisibleOnly</a>
