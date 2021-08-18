URLSearchParams.forEach()
=========================

The `forEach()` method of the [`URLSearchParams`](../urlsearchparams) interface allows iteration through all values contained in this object via a callback function.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    searchParams.forEach(callback);

### Parameters

callback  
A callback function that is executed against each parameter, with the param value provided as its parameter.

### Return value

Void.

Examples
--------

    // Create a test URLSearchParams object
    var searchParams = new URLSearchParams("key1=value1&key2=value2");

    // Log the values
    searchParams.forEach(function(value, key) {
      console.log(value, key);
    });

The result is:

    value1 key1
    value2 key2

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#interface-urlsearchparams">URL<br />
<span class="small">The definition of 'forEach() (see "iterable")' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`forEach`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/forEach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/forEach</a>
