FormData.values()
=================

The `FormData.values()` method returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing to go through all values contained in this object. The values are [`USVString`](../usvstring) or [`Blob`](../blob) objects.

**Note**: This method is available in [Web Workers](../web_workers_api).

Syntax
------

    formData.values();

### Return value

Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols).

Example
-------

    // Create a test FormData object
    var formData = new FormData();
    formData.append('key1', 'value1');
    formData.append('key2', 'value2');

    // Display the values
    for (var value of formData.values()) {
       console.log(value);
    }

The result is:

    value1
    value2

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-formdata">XMLHttpRequest<br />
<span class="small">The definition of 'values() (as iterator&lt;&gt;)' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`values`

50

18

44

No

37

11.1

50

50

44

37

11.3

5.0

See also
--------

-   [`XMLHTTPRequest`](../xmlhttprequest)
-   [Using XMLHttpRequest](../xmlhttprequest/using_xmlhttprequest)
-   [Using FormData objects](using_formdata_objects)
-   [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormData/values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormData/values</a>
