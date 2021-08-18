URLSearchParams.toString()
==========================

The `toString()` method of the [`URLSearchParams`](../urlsearchparams) interface returns a query string suitable for use in a URL.

**Note**: This method returns the query string without the question mark. This is different from [window.location.search](../htmlanchorelement/search), which includes it.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    URLSearchParams.toString()

### Parameters

None.

### Return value

A [`DOMString`](../domstring), without the question mark. (Returns an empty string if no search parameters have been set.)

Examples
--------

    let url = new URL('https://example.com?foo=1&bar=2');
    let params = new URLSearchParams(url.search.slice(1));

    //Add a second foo parameter.
    params.append('foo', 4);
    console.log(params.toString());
    //Prints 'foo=1&bar=2&foo=4'

    // note: params can also be directly created
    let url = new URL('https://example.com?foo=1&bar=2');
    let params = url.searchParams;

    // or even simpler
    let params = new URLSearchParams('foo=1&bar=2');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#interface-urlsearchparams">URL<br />
<span class="small">The definition of 'toString() (see "stringifier")' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   The [`URL`](../url) interface.
-   [Google Developers: Easy URL manipulation with URLSearchParams](https://developers.google.com/web/updates/2016/01/urlsearchparams?hl=en)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/toString</a>
