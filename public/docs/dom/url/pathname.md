URL.pathname
============

The `pathname` property of the [`URL`](../url) interface is a [`USVString`](../usvstring) containing an initial `'/'` followed by the path of the URL not including the query string or fragment (or the empty string if there is no path).

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    const path = url.pathname
    url.pathname = newPath

### Value

A [`USVString`](../usvstring).

Examples
--------

    const url = new URL('https://developer.mozilla.org/en-US/docs/Web/API/URL/pathname?q=value');
    console.log(url.pathname); // Logs "/en-US/docs/Web/API/URL/pathname"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-url-pathname">URL<br />
<span class="small">The definition of 'URL.pathname' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pathname`

32

13

53

22-53

`pathname` and `search` returned the wrong values so that for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return "/x?a=true&b=false" and `search` would return "", rather than "/x" and "?a=true&b=false" respectively.

No

19

10

4.4.3

32

53

22-53

`pathname` and `search` returned the wrong values so that for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return "/x?a=true&b=false" and `search` would return "", rather than "/x" and "?a=true&b=false" respectively.

19

Yes

2.0

See also
--------

-   The [`URL`](../url) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/pathname" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/pathname</a>
