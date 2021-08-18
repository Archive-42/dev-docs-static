# FormData.get()

The `get()` method of the [`FormData`](../formdata) interface returns the first value associated with a given key from within a `FormData` object. If you expect multiple values and want all of them, use the [`getAll()`](getall) method instead.

**Note**: This method is available in [Web Workers](../web_workers_api).

## Syntax

    formData.get(name);

### Parameters

`name`  
A [`USVString`](../usvstring) representing the name of the key you want to retrieve.

### Return value

A [`FormDataEntryValue`](../formdataentryvalue) containing the value. If the key doesn't exist, the method returns null.

## Example

The following line creates an empty `FormData` object:

    var formData = new FormData();

If we add two `username` values using [`FormData.append`](append):

    formData.append('username', 'Chris');
    formData.append('username', 'Bob');

The following `get()` function will only return the first `username` value appended:

    formData.get('username'); // Returns "Chris"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-formdata-get">XMLHttpRequest<br />
<span class="small">The definition of 'get()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

## See also

- [`XMLHTTPRequest`](../xmlhttprequest)
- [Using XMLHttpRequest](../xmlhttprequest/using_xmlhttprequest)
- [Using FormData objects](using_formdata_objects)
- [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormData/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormData/get</a>
