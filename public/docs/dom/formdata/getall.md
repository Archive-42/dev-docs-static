FormData.getAll()
=================

The `getAll()` method of the [`FormData`](../formdata) interface returns all the values associated with a given key from within a `FormData` object.

**Note**: This method is available in [Web Workers](../web_workers_api).

Syntax
------

    formData.getAll(name);

### Parameters

`name`  
A [`USVString`](../usvstring) representing the name of the key you want to retrieve.

### Returns

An array of [`FormDataEntryValue`](../formdataentryvalue)s whose key matches the value passed in the `name` parameter. If the key doesn't exist, the method returns an empty list.

Example
-------

The following line creates an empty `FormData` object:

    var formData = new FormData();

If we add two `username` values using [`FormData.append`](append):

    formData.append('username', 'Chris');
    formData.append('username', 'Bob');

The following `getAll()` function will return both `username` values in an array:

    formData.getAll('username'); // Returns ["Chris", "Bob"]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-formdata-getall">XMLHttpRequest<br />
<span class="small">The definition of 'getAll()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getAll`

50

18

39

No

37

11.1

50

50

39

37

11.3

5.0

See also
--------

-   [`XMLHTTPRequest`](../xmlhttprequest)
-   [Using XMLHttpRequest](../xmlhttprequest/using_xmlhttprequest)
-   [Using FormData objects](using_formdata_objects)
-   [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormData/getAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormData/getAll</a>
