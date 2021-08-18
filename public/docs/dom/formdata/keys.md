FormData.keys()
===============

The `FormData.keys()` method returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing to go through all keys contained in this object. The keys are [`USVString`](../usvstring) objects.

**Note**: This method is available in [Web Workers](../web_workers_api).

Syntax
------

    formData.keys();

### Return value

Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols).

Example
-------

    // Create a test FormData object
    var formData = new FormData();
    formData.append('key1', 'value1');
    formData.append('key2', 'value2');

    // Display the keys
    for (var key of formData.keys()) {
       console.log(key);
    }

The result is:

    key1
    key2

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-formdata">XMLHttpRequest<br />
<span class="small">The definition of 'keys() (as iterator&lt;&gt;)' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

50

18

44

No

Yes

11.1

50

50

44

?

11.3

5.0

See also
--------

-   [`XMLHTTPRequest`](../xmlhttprequest)
-   [Using XMLHttpRequest](../xmlhttprequest/using_xmlhttprequest)
-   [Using FormData objects](using_formdata_objects)
-   [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormData/keys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormData/keys</a>
