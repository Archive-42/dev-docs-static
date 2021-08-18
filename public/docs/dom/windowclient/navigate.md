WindowClient.navigate()
=======================

The `navigate()` method of the [`WindowClient`](../windowclient) interface loads a specified URL into a controlled client page then returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the existing [`WindowClient`](../windowclient).

Syntax
------

    windowClient.navigate(url).then(function(windowClient) {
      // do something with your WindowClient after navigation
    });

### Parameters

`url`  
The location to navigate to.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the existing [`WindowClient`](../windowclient).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-windowclient-navigate">Service Workers<br />
<span class="small">The definition of 'navigate()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`navigate`

49

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

?

No

No

49

44

?

No

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowClient/navigate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowClient/navigate</a>
