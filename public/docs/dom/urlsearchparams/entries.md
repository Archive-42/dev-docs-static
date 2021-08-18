URLSearchParams.entries()
=========================

The `entries()` method of the [`URLSearchParams`](../urlsearchparams) interface returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing iteration through all key/value pairs contained in this object. The key and value of each pair are [`USVString`](../usvstring) objects.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    searchParams.entries();

### Parameters

None.

### Return value

Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols).

Examples
--------

    // Create a test URLSearchParams object
    var searchParams = new URLSearchParams("key1=value1&key2=value2");

    // Display the key/value pairs
    for(var pair of searchParams.entries()) {
       console.log(pair[0]+ ', '+ pair[1]);
    }

The result is:

    key1, value1
    key2, value2

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#interface-urlsearchparams">URL<br />
<span class="small">The definition of 'entries() (see "iterable")' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`entries`

49

17

44

No

36

Yes

49

49

44

36

Yes

5.0

See also
--------

-   The [`URL`](../url) interface.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/entries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/entries</a>
