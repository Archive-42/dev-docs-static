XMLHttpRequest.upload
=====================

The [`XMLHttpRequest`](../xmlhttprequest) `upload` property returns an <span class="page-not-created">`XMLHttpRequestUpload`</span> object that can be observed to monitor an upload's progress. It is an opaque object, but because it's also an [`XMLHttpRequestEventTarget`](../xmlhttprequesteventtarget), event listeners can be attached to track its process.

**Note:** Attaching event listeners to this object prevents the request from being a "simple request" and will cause a preflight request to be issued if cross-origin; see [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS). Because of this, event listeners need to be registered before calling [`send()`](send) or upload events won't be dispatched.

**Note:** The spec also seems to indicate that event listeners should be attached after [`open()`](open). However, browsers are buggy on this matter, and often need the listeners to be registered *before* [`open()`](open) to work.

The following events can be triggered on an upload object and used to monitor the upload:

<table><thead><tr class="header"><th>Event</th><th>Event listener</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>loadstart</code></td><td><span class="page-not-created"><code>onloadstart</code></span></td><td>The upload has begun.</td></tr><tr class="even"><td><code>progress</code></td><td><span class="page-not-created"><code>onprogress</code></span></td><td>Periodically delivered to indicate the amount of progress made so far.</td></tr><tr class="odd"><td><code>abort</code></td><td><span class="page-not-created"><code>onabort</code></span></td><td>The upload operation was aborted.</td></tr><tr class="even"><td><code>error</code></td><td><span class="page-not-created"><code>onerror</code></span></td><td>The upload failed due to an error.</td></tr><tr class="odd"><td><code>load</code></td><td><span class="page-not-created"><code>onload</code></span></td><td>The upload completed successfully.</td></tr><tr class="even"><td><code>timeout</code></td><td><span class="page-not-created"><code>ontimeout</code></span></td><td>The upload timed out because a reply did not arrive within the time interval specified by the <a href="timeout"><code>XMLHttpRequest.timeout</code></a>.</td></tr><tr class="odd"><td><code>loadend</code></td><td><span class="page-not-created"><code>onloadend</code></span></td><td>The upload finished. This event does not differentiate between success or failure, and is sent at the end of the upload regardless of the outcome. Prior to this event, one of <code>load</code>, <code>error</code>, <code>abort</code>, or <code>timeout</code> will already have been delivered to indicate why the upload ended.</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-upload-attribute">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`upload`

1

12

Yes

10

Yes

10

1

18

Yes

Yes

Yes

1.0

See also
--------

-   [Using XMLHttpRequest](using_xmlhttprequest)
-   [FileHandle API](../file_handle_api)
-   [File and Directory Entries API](../file_and_directory_entries_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/upload" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/upload</a>
