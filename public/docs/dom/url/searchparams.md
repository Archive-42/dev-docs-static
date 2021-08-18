URL.searchParams
================

The `searchParams` readonly property of the [`URL`](../url) interface returns a [`URLSearchParams`](../urlsearchparams) object allowing access to the [`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) decoded query arguments contained in the URL.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    const urlSearchParams = url.searchParams

### Value

A [`URLSearchParams`](../urlsearchparams) object.

Examples
--------

If the URL of your page is `https://example.com/?name=Jonathan%20Smith&age=18` you could parse out the `name` and `age` parameters using:

    let params = (new URL(document.location)).searchParams;
    let name = params.get('name'); // is the string "Jonathan Smith".
    let age = parseInt(params.get('age')); // is the number 18

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-searchparams">URL<br />
<span class="small">The definition of 'searchParams' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`searchParams`

51

17

29

No

38

10

51

51

29

41

10

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/searchParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/searchParams</a>
