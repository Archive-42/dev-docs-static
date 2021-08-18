URL.createObjectURL()
=====================

The `URL.createObjectURL()` static method creates a [`DOMString`](../domstring) containing a URL representing the object given in the parameter. The URL lifetime is tied to the [`document`](../document) in the window on which it was created. The new object URL represents the specified [`File`](../file) object or [`Blob`](../blob) object.

To release an object URL, call [`revokeObjectURL()`](revokeobjecturl).

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Note:** This feature is *not* available in [Service Workers](../service_worker_api) due to its potential to create memory leaks.

Syntax
------

    const objectURL = URL.createObjectURL(object)

### Parameters

`object`  
A [`File`](../file), [`Blob`](../blob), or [`MediaSource`](../mediasource) object to create an object URL for.

### Return value

A [`DOMString`](../domstring) containing an object URL that can be used to reference the contents of the specified source `object`.

Examples
--------

See [Using object URLs to display images](../file/using_files_from_web_applications#example_using_object_urls_to_display_images).

Usage notes
-----------

### Memory management

Each time you call `createObjectURL()`, a new object URL is created, even if you've already created one for the same object. Each of these must be released by calling [`URL.revokeObjectURL()`](revokeobjecturl) when you no longer need them.

Browsers will release object URLs automatically when the document is unloaded; however, for optimal performance and memory usage, if there are safe times when you can explicitly unload them, you should do so.

### Using object URLs for media streams

In older versions of the Media Source specification, attaching a stream to a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element required creating an object URL for the [`MediaStream`](../mediastream). This is no longer necessary, and browsers are removing support for doing this.

**Important:** If you still have code that relies on [`createObjectURL()`](createobjecturl) to attach streams to media elements, you need to update your code to set [`srcObject`](../htmlmediaelement/srcobject) to the `MediaStream` directly.

Specifications
--------------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-createObjectURL">File API<br />
<span class="small">The definition of 'createObjectURL()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/media-source/#dom-url-createobjecturl">Media Source Extensions<br />
<span class="small">The definition of 'URL' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td><p>MediaSource extension.</p><p>Older versions of this specification used <code>createObjectURL()</code> for <a href="../mediastream"><code>MediaStream</code></a> objects; this is no longer supported.</p></td></tr></tbody></table>

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

`createObjectURL`

19

12

19

`createObjectURL()` is no longer available within the context of a `ServiceWorker`.

10

If the underlying object does not have a content type set, using this URL as the `src` of an `img` tag fails intermittently with error DOM7009.

15

6

≤37

25

19

`createObjectURL()` is no longer available within the context of a `ServiceWorker`.

14

6

1.5

`no_MediaStream_argument`

?

See [here](https://crbug.com/591719) for progress on deprecation.

?

See [here](https://crbug.com/591719) for progress on deprecation.

62

?

?

See [here](https://crbug.com/591719) for progress on deprecation.

?

See [here](https://webkit.org/b/167518) for progress on deprecation.

?

See [here](https://crbug.com/591719) for progress on deprecation.

?

See [here](https://crbug.com/591719) for progress on deprecation.

62

?

See [here](https://crbug.com/591719) for progress on deprecation.

?

See [here](https://webkit.org/b/167518) for progress on deprecation.

?

See [here](https://crbug.com/591719) for progress on deprecation.

See also
--------

-   [Using files from web applications](../file/using_files_from_web_applications)
-   [Using object URLs to display images](../file/using_files_from_web_applications#example_using_object_urls_to_display_images)
-   [`URL.revokeObjectURL()`](revokeobjecturl)
-   [`HTMLMediaElement.srcObject`](../htmlmediaelement/srcobject)
-   [`FileReader.readAsDataURL()`](../filereader/readasdataurl)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/createObjectURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/createObjectURL</a>
