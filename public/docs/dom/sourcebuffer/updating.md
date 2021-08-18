SourceBuffer.updating
=====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `updating` read-only property of the [`SourceBuffer`](../sourcebuffer) interface indicates whether the `SourceBuffer` is currently being updated — i.e. whether an [`SourceBuffer.appendBuffer()`](appendbuffer), [`SourceBuffer.appendStream()`](appendstream), or [`SourceBuffer.remove()`](remove) operation is currently in progress.

Syntax
------

    var isUpdating = sourceBuffer.updating;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Example
-------

TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#idl-def-sourcebuffer-updating">Media Source Extensions<br />
<span class="small">The definition of 'updating' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`updating`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

No

14

No

3.0

See also
--------

-   [`MediaSource`](../mediasource)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/updating" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/updating</a>
