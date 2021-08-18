ServiceWorkerGlobalScope.onpushsubscriptionchange
=================================================

The `ServiceWorkerGlobalScope.onpushsubscriptionchange` event of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface is fired to indicate a change in push subscription that was triggered outside the application's control, e.g. when browser refresh the push subscription.

Previously, it was defined as the event interface that is fired whenever a push subscription has been invalidated (or is about to become so). This offers an opportunity to resubscribe in order to continue receiving push messages, if desired. This might happen if, for example, the push service sets an expiration time a subscription.

Syntax
------

    ServiceWorkerGlobalScope.onpushsubscriptionchange = function() { ... }
    self.addEventListener('pushsubscriptionchange', function() { ... })

Example
-------

    self.addEventListener('pushsubscriptionchange', function() {
      // do something, usually resubscribe to push and
      // send the new subscription details back to the
      // server via XHR or Fetch
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-serviceworkerglobalscope-onpushsubscriptionchange">Push API<br />
<span class="small">The definition of 'onpushsubscriptionchange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition (Note: This event is specified in the Push API, but accessed through <a href="../serviceworkerglobalscope"><code>ServiceWorkerGlobalScope</code></a>.)</td></tr></tbody></table>

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

`onpushsubscriptionchange`

40

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

24

11.1

40

40

44

24

11.3

4.0

See also
--------

-   [Push API](../push_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onpushsubscriptionchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onpushsubscriptionchange</a>
