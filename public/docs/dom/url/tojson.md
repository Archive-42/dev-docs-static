URL.toJSON()
============

The `toJSON()` method of the [`URL`](../url) interface returns a [`USVString`](../usvstring) containing a serialized version of the URL, although in practice it seems to have the same effect as [`URL.toString()`](tostring).

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    const href = url.toJSON()

### Return value

A [`USVString`](../usvstring).

Examples
--------

    const url = new URL("https://developer.mozilla.org/en-US/docs/Web/API/URL/toString");
    url.toJSON(); // should return the URL as a string

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-tojson">URL<br />
<span class="small">The definition of 'toJSON()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`toJSON`

71

17

54

No

58

11

71

71

54

50

11

10.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/toJSON</a>
