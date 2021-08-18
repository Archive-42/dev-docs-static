URL.toString()
==============

The `URL.toString()` stringifier method returns a [`USVString`](../usvstring) containing the whole URL. It is effectively a read-only version of [`URL.href`](href).

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    const href = url.toString()

### Return value

A [`USVString`](../usvstring).

Examples
--------

    const url = new URL("https://developer.mozilla.org/en-US/docs/Web/API/URL/toString");
    url.toString(); // should return the URL as a string

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#URL-stringification-behavior">URL<br />
<span class="small">The definition of 'stringifier' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`toString`

19

17

54

No

15

6.1

≤37

25

54

14

6.1

6.0

See also
--------

-   The [`URL`](../url) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/toString</a>
