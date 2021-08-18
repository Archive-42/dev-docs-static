# FormData

The `FormData` interface provides a way to easily construct a set of key/value pairs representing form fields and their values, which can then be easily sent using the [`XMLHttpRequest.send()`](xmlhttprequest/send) method. It uses the same format a form would use if the encoding type were set to `"multipart/form-data"`.

You can also pass it directly to the [`URLSearchParams`](urlsearchparams) constructor if you want to generate query parameters in the way a [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) would do if it were using simple `GET` submission.

An object implementing `FormData` can directly be used in a [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) structure, instead of [`entries()`](formdata/entries): `for (var p of myFormData)` is equivalent to `for (var p of myFormData.entries())`.

**Note**: This feature is available in [Web Workers](web_workers_api).

## Constructor

[`FormData()`](formdata/formdata)  
Creates a new `FormData` object.

## Methods

[`FormData.append()`](formdata/append)  
Appends a new value onto an existing key inside a `FormData` object, or adds the key if it does not already exist.

[`FormData.delete()`](formdata/delete)  
Deletes a key/value pair from a `FormData` object.

[`FormData.entries()`](formdata/entries)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing to go through all key/value pairs contained in this object.

[`FormData.get()`](formdata/get)  
Returns the first value associated with a given key from within a `FormData` object.

[`FormData.getAll()`](formdata/getall)  
Returns an array of all the values associated with a given key from within a `FormData`.

[`FormData.has()`](formdata/has)  
Returns a boolean stating whether a `FormData` object contains a certain key.

[`FormData.keys()`](formdata/keys)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing to go through all keys of the key/value pairs contained in this object.

[`FormData.set()`](formdata/set)  
Sets a new value for an existing key inside a `FormData` object, or adds the key/value if it does not already exist.

[`FormData.values()`](formdata/values)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing to go through all values contained in this object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#interface-formdata">XMLHttpRequest<br />
<span class="small">The definition of 'FormData' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>FormData defined in XHR spec</td></tr></tbody></table>

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

`FormData`

7

12

4

Prior to Firefox 7, specifying a [`Blob`](https://developer.mozilla.org/docs/Web/API/Blob) as the data to append to the object, the filename reported in the `Content-Disposition` HTTP header was an empty string, resulting in errors on some servers. Starting with Firefox 7, the filename `blob` is sent.

10

12

5

≤37

XHR in Android 4.0 sends empty content for `FormData` with `blob`.

18

4

Prior to Firefox 7, specifying a [`Blob`](https://developer.mozilla.org/docs/Web/API/Blob) as the data to append to the object, the filename reported in the `Content-Disposition` HTTP header was an empty string, resulting in errors on some servers. Starting with Firefox 7, the filename `blob` is sent.

12

5

1.0

`FormData`

7

12

4

10

12

5

≤37

18

4

12

5

1.0

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

`entries`

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

`forEach`

50

18

47

No

37

11.1

50

50

47

37

11.3

5.0

`get`

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

`worker_support`

Yes

≤18

39

No

Yes

13.1

Yes

Yes

Yes

Yes

13.4

Yes

`@@iterator`

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

## See also

- [`XMLHTTPRequest`](xmlhttprequest)
- [Using XMLHttpRequest](xmlhttprequest/using_xmlhttprequest)
- [Using FormData objects](formdata/using_formdata_objects)
- [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormData</a>
