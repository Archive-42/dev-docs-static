URLSearchParams.delete()
========================

The `delete()` method of the [`URLSearchParams`](../urlsearchparams) interface deletes the given search parameter and all its associated values, from the list of all search parameters.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    URLSearchParams.delete(name)

### Parameters

name  
The name of the parameter to be deleted.

### Return value

Void

Examples
--------

    let url = new URL('https://example.com?foo=1&bar=2&foo=3');
    let params = new URLSearchParams(url.search);

    // Delete the foo parameter.
    params.delete('foo'); //Query string is now: 'bar=2'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-urlsearchparams-delete">URL<br />
<span class="small">The definition of 'delete()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`delete`

49

17

29

No

36

Yes

Removing a non-existent query parameter doesn't remove `?` from the URL. See [bug 193022](https://webkit.org/b/193022).

49

49

29

36

Yes

Removing a non-existent query parameter doesn't remove `?` from the URL. See [bug 193022](https://webkit.org/b/193022).

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/delete</a>
