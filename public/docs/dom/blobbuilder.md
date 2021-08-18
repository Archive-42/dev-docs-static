# BlobBuilder

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note**

The `BlobBuilder` interface has been deprecated in favor of the newly introduced [`Blob`](blob) constructor.

The `BlobBuilder` interface provides an easy way to construct [`Blob`](blob) objects. Just create a `BlobBuilder` and append chunks of data to it by calling the `append()` method. When you're done building your blob, call `getBlob()` to retrieve a [`Blob`](blob) containing the data you sent into the blob builder.

## Method overview

<table><tbody><tr class="odd"><td><code>void append(in ArrayBuffer data);</code></td></tr><tr class="even"><td><code>void append(in Blob data);</code></td></tr><tr class="odd"><td><code>void append(in String data, [optional] in String endings);</code></td></tr><tr class="even"><td><code>Blob getBlob([optional] in DOMString contentType);</code></td></tr><tr class="odd"><td><code>File getFile(in DOMString name, [optional] in DOMString contentType);</code></td></tr></tbody></table>

## Methods

### append()

Appends the contents of the specified JavaScript object to the [`Blob`](blob) being built. If the value you specify isn't a [`Blob`](blob), [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), or [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), the value is coerced to a string before being appended to the blob.

    void append(
      in ArrayBuffer data
    );

    void append(
      in Blob data
    );

    void append(
      in String data,
      [optional] in String endings
    );

###### Parameters

`data`  
The data to append to the [`Blob`](blob) being constructed.

`endings`  
Specifies how strings containing `\n` are to be written out. This can be `"transparent"` (endings unchanged) or `"native"` (endings changed to match host OS filesystem convention). The default value is `"transparent"`.

### getBlob()

Returns the [`Blob`](blob) object that has been constructed using the data passed through calls to `append()`.

    Blob getBlob(
      in DOMString contentType Optional
    );

###### Parameters

`contentType` <span class="badge inline optional">Optional</span>  
The MIME type of the data to be returned in the [`Blob`](blob). This will be the value of the `Blob` object's type property.

###### Return value

A [`Blob`](blob) object containing all of the data passed to any calls to `append()` made since the `BlobBuilder` was created. This also resets the `BlobBuilder` so that the next call to `append()` is starting a new, empty blob.

### getFile() <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>

Returns a [`File`](file) object.

    File getFile(
      in DOMString name,
      [optional] in DOMString contentType
    );

###### Parameters

`name`  
The file name.

`contentType` <span class="badge inline optional">Optional</span>  
The MIME type of the data to be returned in the [`File`](file). This will be the value of the `File` object's type property.

###### Return value

A [`File`](file) object.

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

`BlobBuilder`

8-24

12-79

6-18

Starting in Firefox 14, using `MozBlobBuilder` will show a warning message in the web console that the use of `MozBlobBuilder` is deprecated and suggests to use [`Blob`](https://developer.mozilla.org/docs/Web/API/Blob) constructor instead.

10

No

No

3-≤37

18-25

6-18

Starting in Firefox 14, using `MozBlobBuilder` will show a warning message in the web console that the use of `MozBlobBuilder` is deprecated and suggests to use [`Blob`](https://developer.mozilla.org/docs/Web/API/Blob) constructor instead.

No

No

1.0-1.5

## See also

- [File API Specification: BlobBuilder](https://dev.w3.org/2009/dap/file-system/file-writer.html#idl-def-BlobBuilder)ED
- [`Blob`](blob)
- [`File`](file)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BlobBuilder" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BlobBuilder</a>
