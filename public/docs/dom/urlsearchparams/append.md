URLSearchParams.append()
========================

The `append()` method of the [`URLSearchParams`](../urlsearchparams) interface appends a specified key/value pair as a new search parameter.

As shown in the example below, if the same key is appended multiple times it will appear in the parameter string multiple times for each value.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    URLSearchParams.append(name, value)

### Parameters

name  
The name of the parameter to append.

value   
The value of the parameter to append.

### Return value

Void.

Examples
--------

    let url = new URL('https://example.com?foo=1&bar=2');
    let params = new URLSearchParams(url.search.slice(1));

    //Add a second foo parameter.
    params.append('foo', 4);
    //Query string is now: 'foo=1&bar=2&foo=4'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-urlsearchparams-append">URL<br />
<span class="small">The definition of 'append()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`append`

49

17

29

No

36

10.1

49

49

29

36

10.3

5.0

See also
--------

-   Other URL-related interfaces: [`URL`](../url), <span class="page-not-created">`HTMLHyperlinkElementUtils`</span>.
-   [Google Developers: Easy URL manipulation with URLSearchParams](https://developers.google.com/web/updates/2016/01/urlsearchparams?hl=en)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/append" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/append</a>
