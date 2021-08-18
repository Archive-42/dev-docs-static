MediaError.code
===============

The read-only property `MediaError.code` returns a numeric value which represents the kind of error that occurred on a media element. To get a text string with specific diagnostic information, see [`MediaError.message`](message).

Syntax
------

    var myError = mediaError.code;

### Value

A numeric value indicating the general type of error which occurred. The possible values are described below, in [Media error code constants](#media_error_code_constants).

#### Media error code constants

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>MEDIA_ERR_ABORTED</code></td><td><code>1</code></td><td>The fetching of the associated resource was aborted by the user's request.</td></tr><tr class="even"><td><code>MEDIA_ERR_NETWORK</code></td><td><code>2</code></td><td>Some kind of network error occurred which prevented the media from being successfully fetched, despite having previously been available.</td></tr><tr class="odd"><td><code>MEDIA_ERR_DECODE</code></td><td><code>3</code></td><td>Despite having previously been determined to be usable, an error occurred while trying to decode the media resource, resulting in an error.</td></tr><tr class="even"><td><code>MEDIA_ERR_SRC_NOT_SUPPORTED</code></td><td><code>4</code></td><td>The associated resource or media provider object (such as a <a href="../mediastream"><code>MediaStream</code></a>) has been found to be unsuitable.</td></tr></tbody></table>

Example
-------

This example creates a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, establishes an error handler for it, and then sets the element's [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-src) attribute to the video resource to present in the element. The error handler outputs a message

    var obj = document.createElement('video');
    obj.onerror = function() {console.log("Error with media: " + obj.error.code);}
    obj.src="https://example.com/blahblah.mp4";

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-mediaerror-code">HTML Living Standard<br />
<span class="small">The definition of 'MediaError.code' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`code`

Yes

12

3.5

9

Yes

10

Yes

Yes

4

Yes

10

Yes

See also
--------

-   The interface defining it, [`MediaError`](../mediaerror).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaError/code" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaError/code</a>
