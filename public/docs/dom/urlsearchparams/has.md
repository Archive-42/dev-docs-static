URLSearchParams.has()
=====================

The `has()` method of the [`URLSearchParams`](../urlsearchparams) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether a parameter with the specified name exists.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var hasName = URLSearchParams.has(name)

### Parameters

name  
The name of the parameter to find.

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Examples
--------

    let url = new URL('https://example.com?foo=1&bar=2');
    let params = new URLSearchParams(url.search.slice(1));

    params.has('bar') === true; //true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-urlsearchparams-has">URL<br />
<span class="small">The definition of 'has()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`has`

49

17

29

No

36

Yes

49

49

29

36

Yes

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/has</a>
