Navigator.setAppBadge()
=======================

The `setAppBadge()` method of the [`Navigator`](../navigator) interface a badge on the icon associated with this app. If a value is passed to the method, this will be set as the value of the badge. Otherwise the badge will display as a dot, or other indicator as defined by the platform.

Syntax
------

    let promise = Navigator.setAppBadge(contents);

### Parameters

 `contents`<span class="badge inline optional">Optional</span>   
A [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) which will be used as the value of the badge. If `contents` is `0` then the badge will be set to `nothing`, indicating a cleared badge.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

`NotSupportedError`  
The [`Navigator`](../navigator) does not have a document that this action can be acted on.

Examples
--------

In the example below an unread count is passed to `setAppBadge()`. The badge should then display `30`.

    const unread = 30;
    navigator.setAppBadge(unread);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/badging/#setappbadge-method">Badging API<br />
<span class="small">The definition of 'setAppBadge' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`setAppBadge`

81

81

No

No

No

No

81

81

No

58

No

13.0

See also
--------

-   [Badging for app icons](https://web.dev/badging-api/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/setAppBadge" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/setAppBadge</a>
