URL.password
============

The `password` property of the [`URL`](../url) interface is a [`USVString`](../usvstring) containing the password specified before the domain name.

If it is set without first setting the [`username`](username) property, it silently fails.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    const passwordString = url.password
    url.password = newPassword

### Value

A [`USVString`](../usvstring).

Examples
--------

    const url = new URL('https://anonymous:flabada@developer.mozilla.org/en-US/docs/Web/API/URL/password');
    console.log(url.password) // Logs "flabada"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-password">URL<br />
<span class="small">The definition of 'URL.password' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`password`

32

12

26

No

19

10

≤37

32

26

19

Yes

6.0

See also
--------

-   The [`URL`](../url) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/password" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/password</a>
