URLSearchParams.sort()
======================

The `URLSearchParams.sort()` method sorts all key/value pairs contained in this object in place and returns `undefined`. The sort order is according to unicode code points of the keys. This method uses a stable sorting algorithm (i.e. the relative order between key/value pairs with equal keys will be preserved).

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    searchParams.sort();

### Parameters

None.

### Return value

`undefined`.

Examples
--------

    // Create a test URLSearchParams object
    var searchParams = new URLSearchParams("c=4&a=2&b=3&a=1");

    // Sort the key/value pairs
    searchParams.sort();

    // Display the sorted query string
    console.log(searchParams.toString());

The result is:

    a=2&a=1&b=3&c=4

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-urlsearchparams-sort">URL<br />
<span class="small">The definition of 'sort()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`sort`

61

17

54

No

48

Yes

61

61

54

45

Yes

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/sort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/sort</a>
