FormData.append()
=================

The `append()` method of the [`FormData`](../formdata) interface appends a new value onto an existing key inside a `FormData` object, or adds the key if it does not already exist.

The difference between [`FormData.set`](set) and `append()` is that if the specified key already exists, [`FormData.set`](set) will overwrite all existing values with the new one, whereas `append()` will append the new value onto the end of the existing set of values.

**Note**: This method is available in [Web Workers](../web_workers_api).

Syntax
------

There are two versions of this method: a two and a three parameter version:

    formData.append(name, value);
    formData.append(name, value, filename);

### Parameters

`name`  
The name of the field whose data is contained in `value`.

`value`  
The field's value. This can be a [`USVString`](../usvstring) or [`Blob`](../blob) (including subclasses such as [`File`](../file)). If none of these are specified the value is converted to a string.

 `filename `<span class="badge inline optional">Optional</span>   
The filename reported to the server (a [`USVString`](../usvstring)), when a [`Blob`](../blob) or [`File`](../file) is passed as the second parameter. The default filename for [`Blob`](../blob) objects is "blob". The default filename for [`File`](../file) objects is the file's filename.

**Note:** If you specify a [`Blob`](../blob) as the data to append to the `FormData` object, the filename that will be reported to the server in the "Content-Disposition" header used to vary from browser to browser.

### Returns

Void.

Example
-------

The following line creates an empty `FormData` object:

    var formData = new FormData(); // Currently empty

You can add key/value pairs to this using [`FormData.append`](append):

    formData.append('username', 'Chris');
    formData.append('userpic', myFileInput.files[0], 'chris.jpg');

As with regular form data, you can append multiple values with the same name. For example (and being compatible with PHP's naming conventions by adding \[\] to the name):

    formData.append('userpic[]', myFileInput.files[0], 'chris1.jpg');
    formData.append('userpic[]', myFileInput.files[1], 'chris2.jpg');

This technique makes it simpler to process multi-file uploads because the resultant data structure is more conducive to looping.

If the sent value is different than String or Blob it will be automatically converted to String:

    formData.append('name', true);
    formData.append('name', 74);
    formData.append('name', 'John');

    formData.getAll('name'); // ["true", "74", "John"]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-formdata-append">XMLHttpRequest<br />
<span class="small">The definition of 'append()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`append`

7

12

4

Prior to Firefox 7, specifying a [`Blob`](https://developer.mozilla.org/docs/Web/API/Blob) as the data to append to the object, the filename reported in the `Content-Disposition` HTTP header was an empty string, resulting in errors on some servers. Starting with Firefox 7, the filename `blob` is sent.

10

With the "Include local directory pass when uploading files to a server" option enabled, IE will change the filename inside the [`Blob`](https://developer.mozilla.org/docs/Web/API/Blob) on the fly. To have direct control of the sent filename, the developer should send the filename as the third parameter value, i.e. `formData.append(name, value, filename)`.

12

5

3

XHR in Android 4.0 sends empty content for `FormData` with `blob`.

18

4

Prior to Firefox 7, specifying a [`Blob`](https://developer.mozilla.org/docs/Web/API/Blob) as the data to append to the object, the filename reported in the `Content-Disposition` HTTP header was an empty string, resulting in errors on some servers. Starting with Firefox 7, the filename `blob` is sent.

12

5

1.0

`AppendWithFilename`

16

12

22

Yes

≤15

6

4.4

18

22

≤14

6

1.0

See also
--------

-   [`XMLHTTPRequest`](../xmlhttprequest)
-   [Using XMLHttpRequest](../xmlhttprequest/using_xmlhttprequest)
-   [Using FormData objects](using_formdata_objects)
-   [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormData/append" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormData/append</a>
