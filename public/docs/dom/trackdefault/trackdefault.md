TrackDefault.TrackDefault()
===========================

**Draft**

This page is not complete.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `TrackDefault()` constructor of the [`TrackDefault`](../trackdefault) interface constructs and returns a new `TrackDefault` object.

Syntax
------

    var trackDefault = new TrackDefault(type, language, label, kinds, byteStreamTrackID);

### Parameters

type  
A [`DOMString`](../domstring) specifying a media segment data type for the [`SourceBuffer`](../sourcebuffer) to contain. Can be `audio`, `video`, or `text`.

language  
A [`DOMString`](../domstring) specifying a default language for the [`SourceBuffer`](../sourcebuffer) to use when an [initialization segment](https://w3c.github.io/media-source/#init-segment) does not contain language information for a new track.

label  
A [`DOMString`](../domstring) specifying a default label for the [`SourceBuffer`](../sourcebuffer) to use when an [initialization segment](https://w3c.github.io/media-source/#init-segment) does not contain label information for a new track.

kinds  
An array (sequence) of [`DOMString`](../domstring)s specifying default kinds for the [`SourceBuffer`](../sourcebuffer) to use when an [initialization segment](https://w3c.github.io/media-source/#init-segment) does not contain kind information for a new track.

byteStreamTrackID <span class="badge inline optional">Optional</span>   
A [`DOMString`](../domstring) specifying the ID of the specific track that the [`SourceBuffer`](../sourcebuffer) should apply to. If not specified, this value will be an empty string and the `SourceBuffer` can contain any tracks of the specified `type`.

### Errors

when this constructor is invoked, the following errors can occur:

<table><thead><tr class="header"><th>Error</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>InvalidAccessError</code></td><td>The supplied <code>language</code> is not a valid language code, e.g. <code>en-US</code>.</td></tr><tr class="even"><td><code>TypeError</code></td><td>there are values specified in the <code>kinds</code> array that do not apply to the specified <code>type</code>.</td></tr></tbody></table>

Example
-------

TBD

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

`TrackDefault`

No

≤18

No

No

No

No

No

No

No

No

No

No

See also
--------

-   [`MediaSource`](../mediasource)
-   [`SourceBuffer`](../sourcebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrackDefault/TrackDefault" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrackDefault/TrackDefault</a>
