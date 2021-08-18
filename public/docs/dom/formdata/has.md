FormData.has()
==============

The `has()` method of the [`FormData`](../formdata) interface returns a boolean stating whether a `FormData` object contains a certain key.

**Note**: This method is available in [Web Workers](../web_workers_api).

Syntax
------

    formData.has(name);

### Parameters

`name`  
A [`USVString`](../usvstring) representing the name of the key you want to test for.

### Returns

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Example
-------

The following line creates an empty `FormData` object:

    var formData = new FormData();

The following snippet shows the results of testing for the existence of `username` in the `FormData` object, before and after appending a `username` value to it with [`FormData.append`](append):

    formData.has('username'); // Returns false
    formData.append('username', 'Chris');
    formData.has('username'); // Returns true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-formdata-has">XMLHttpRequest<br />
<span class="small">The definition of 'has()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`has`

50

18

39

No

Yes

11.1

50

50

Yes

Yes

11.3

5.0

See also
--------

-   [`XMLHTTPRequest`](../xmlhttprequest)
-   [Using XMLHttpRequest](../xmlhttprequest/using_xmlhttprequest)
-   [Using FormData objects](using_formdata_objects)
-   [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormData/has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormData/has</a>
