SourceBufferList: indexed property getter
=========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The **indexed property getter** of the [`SourceBufferList`](../sourcebufferlist) interface allows the `SourceBuffer` objects in the list to be accessed with an array operator (i.e. `[]`.)

Syntax
------

    var mySourceBuffer = sourceBufferList[index];

### Parameters

index  
The index position of the [`SourceBuffer`](../sourcebuffer) object you want to return.

### Return value

A [`SourceBuffer`](../sourcebuffer) object.

### Exceptions

No specific exceptions are thrown, but if the supplied index is great than or equal to [`SourceBufferList.length`](length), the operation will return `undefined`.

Example
-------

TBD.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#dfn-sourcebufferlist-getter">Media Source Extensions<br />
<span class="small">The definition of 'SourceBuffer() getter' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`SourceBuffer`

45

12

42

11

Only works on Windows 8+.

32

8

45

45

No

32

No

5.0

See also
--------

-   [`MediaSource`](../mediasource)
-   [`SourceBuffer`](../sourcebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBufferList/SourceBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBufferList/SourceBuffer</a>
