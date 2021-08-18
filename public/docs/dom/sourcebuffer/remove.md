SourceBuffer.remove()
=====================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `remove()` method of the [`SourceBuffer`](../sourcebuffer) interface removes media segments within a specific time range from the `SourceBuffer`. This method can only be called when [`SourceBuffer.updating`](updating) equals `false`. If `SourceBuffer.updating` is not equal to `false`, call [`SourceBuffer.abort()`](abort).

Syntax
------

    sourceBuffer.remove(start, end);

### Parameters

start  
A double representing the start of the time range, in seconds.

end  
A double representing the end of the time range, in seconds.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>InvalidAccessError</code></td><td>The <a href="../mediasource/duration"><code>MediaSource.duration</code></a> property is equal to <code>NaN</code>, the <code>start</code> parameter is negative or greater than <a href="../mediasource/duration"><code>MediaSource.duration</code></a>, or the end parameter is less than or equal to start or equal to <code>NaN</code>.</td></tr><tr class="even"><td><code>InvalidStateError</code></td><td>The <a href="updating"><code>SourceBuffer.updating</code></a> property is equal to <code>true</code>, or this <code>SourceBuffer</code> has been removed from the <a href="../mediasource"><code>MediaSource</code></a>.</td></tr></tbody></table>

Example
-------

TBD.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#dom-sourcebuffer-remove">Media Source Extensions<br />
<span class="small">The definition of 'remove()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`remove`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/remove" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/remove</a>
