URLSearchParams()
=================

The `URLSearchParams()` constructor creates and returns a new [`URLSearchParams`](../urlsearchparams) object.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var URLSearchParams = new URLSearchParams(init);

### Parameters

*`init`* <span class="badge inline optional">Optional</span>

One of:

-   A [`USVString`](../usvstring), which will be parsed from `application/x-www-form-urlencoded` format. A leading `'?'` character is ignored.
-   A sequence of [`USVString`](../usvstring) pairs, representing names/values.
-   A record of [`USVString`](../usvstring) keys and [`USVString`](../usvstring) values.

### Return value

A [`URLSearchParams`](../urlsearchparams) object instance.

Examples
--------

The following example shows how to create a [`URLSearchParams`](../urlsearchparams) object from a URL string.

    // Retrieve params via url.search, passed into ctor
    var url = new URL('https://example.com?foo=1&bar=2');
    var params = new URLSearchParams(url.search);

    // Pass in a string literal
    var params2 = new URLSearchParams("foo=1&bar=2");
    var params2a = new URLSearchParams("?foo=1&bar=2");

    // Pass in a sequence of pairs
    var params3 = new URLSearchParams([["foo", "1"], ["bar", "2"]]);

    // Pass in a record
    var params4 = new URLSearchParams({"foo": "1", "bar": "2"});

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-urlsearchparams-urlsearchparams">URL<br />
<span class="small">The definition of 'URLSearchParams()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`URLSearchParams`

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

`USVString`

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

`record`

61

17

54

No

48

11

61

61

54

45

11

8.0

`sequence`

58

17

53

No

45

11

58

58

53

43

11

7.2

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/URLSearchParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/URLSearchParams</a>
