FormData.delete()
=================

The `delete()` method of the [`FormData`](../formdata) interface deletes a key and its value(s) from a `FormData` object.

**Note**: This method is available in [Web Workers](../web_workers_api).

Syntax
------

    formData.delete(name);

### Parameters

`name`  
The name of the key you want to delete.

### Returns

Void.

Example
-------

The following line creates an empty `FormData` object and prepopulates it with key/value pairs from a form:

    var formData = new FormData(myForm);

You can delete keys and their values using `delete()`:

    formData.delete('username');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-formdata-delete">XMLHttpRequest<br />
<span class="small">The definition of 'delete()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`delete`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormData/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormData/delete</a>
