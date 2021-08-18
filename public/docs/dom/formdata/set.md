# FormData.set()

The `set()` method of the [`FormData`](../formdata) interface sets a new value for an existing key inside a `FormData` object, or adds the key/value if it does not already exist.

The difference between `set()` and [`FormData.append`](append) is that if the specified key does already exist, `set()` will overwrite all existing values with the new one, whereas [`FormData.append`](append) will append the new value onto the end of the existing set of values.

**Note**: This method is available in [Web Workers](../web_workers_api).

## Syntax

There are two versions of this method: a two and a three parameter version:

    formData.set(name, value);
    formData.set(name, value, filename);

#### Parameters

`name`  
The name of the field whose data is contained in `value`.

`value`  
The field's value. This can be a [`USVString`](../usvstring) or [`Blob`](../blob) (including subclasses such as [`File`](../file)). If none of these are specified the value is converted to a string.

`filename `<span class="badge inline optional">Optional</span>  
The filename reported to the server (a [`USVString`](../usvstring)), when a [`Blob`](../blob) or [`File`](../file) is passed as the second parameter. The default filename for [`Blob`](../blob) objects is "blob". The default filename for [`File`](../file) objects is the file's filename.

**Note:** If you specify a [`Blob`](../blob) as the data to append to the `FormData` object, the filename that will be reported to the server in the "Content-Disposition" header used to vary from browser to browser.

## Example

The following line creates an empty `FormData` object:

    var formData = new FormData(); // Currently empty

You can set key/value pairs on this using [`FormData.set`](set):

    formData.set('username', 'Chris');
    formData.set('userpic', myFileInput.files[0], 'chris.jpg');

If the sent value is different than String or Blob it will be automatically converted to String:

    formData.set('name', 72);
    formData.get('name'); // "72"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-formdata-set">XMLHttpRequest<br />
<span class="small">The definition of 'set()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

`set`

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

## See also

- [`XMLHTTPRequest`](../xmlhttprequest)
- [Using XMLHttpRequest](../xmlhttprequest/using_xmlhttprequest)
- [Using FormData objects](using_formdata_objects)
- [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormData/set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormData/set</a>
