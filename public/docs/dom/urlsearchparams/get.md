URLSearchParams.get()
=====================

The `get()` method of the [`URLSearchParams`](../urlsearchparams) interface returns the first value associated to the given search parameter.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    URLSearchParams.get(name)

### Parameters

name  
The name of the parameter to return.

### Return value

A [`USVString`](../usvstring) if the given search parameter is found; otherwise, `null`.

Examples
--------

If the URL of your page is `https://example.com/?name=Jonathan&age=18` you could parse out the 'name' and 'age' parameters using:

    let params = new URLSearchParams(document.location.search.substring(1));
    let name = params.get("name"); // is the string "Jonathan"
    let age = parseInt(params.get("age"), 10); // is the number 18

Requesting a parameter that isn't present in the query string will return `null`:

    let address = params.get("address"); // null

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-urlsearchparams-get">URL<br />
<span class="small">The definition of 'get()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`get`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/get</a>
