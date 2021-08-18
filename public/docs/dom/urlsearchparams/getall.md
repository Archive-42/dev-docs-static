URLSearchParams.getAll()
========================

The `getAll()` method of the [`URLSearchParams`](../urlsearchparams) interface returns all the values associated with a given search parameter as an array.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    URLSearchParams.getAll(name)

### Parameters

name  
The name of the parameter to return.

### Return value

An array of [`USVString`](../usvstring)s.

Examples
--------

    let url = new URL('https://example.com?foo=1&bar=2');
    let params = new URLSearchParams(url.search.slice(1));

    //Add a second foo parameter.
    params.append('foo', 4);

    console.log(params.getAll('foo')) //Prints ["1","4"].

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-urlsearchparams-getall">URL<br />
<span class="small">The definition of 'getAll()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getAll`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/getAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/getAll</a>
