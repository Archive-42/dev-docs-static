URLSearchParams.keys()
======================

The `keys()` method of the [`URLSearchParams`](../urlsearchparams) interface returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing iteration through all keys contained in this object. The keys are [`USVString`](../usvstring) objects.

**Note**: This method is available in [Web Workers](../web_workers_api).

Syntax
------

    searchParams.keys();

### Parameters

None.

### Return value

Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols).

Examples
--------

    // Create a test URLSearchParams object
    var searchParams = new URLSearchParams("key1=value1&key2=value2");

    // Display the keys
    for(var key of searchParams.keys()) {
      console.log(key);
    }

The result is:

    key1
    key2

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#interface-urlsearchparams">URL<br />
<span class="small">The definition of 'keys() (see "iterable")' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`keys`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/keys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/keys</a>
