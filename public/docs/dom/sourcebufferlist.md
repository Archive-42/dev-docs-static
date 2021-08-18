SourceBufferList
================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SourceBufferList` interface represents a simple container list for multiple [`SourceBuffer`](sourcebuffer) objects.

The source buffer list containing the `SourceBuffer`s appended to a particular `MediaSource` can be retrieved using the [`MediaSource.sourceBuffers`](mediasource/sourcebuffers) property. The individual source buffers can be accessed using array operator (i.e. `[]`) or functions such as [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) for example.

Properties
----------

 [`SourceBufferList.length`](sourcebufferlist/length) <span class="badge inline readonly">Read only </span>   
Returns the number of [`SourceBuffer`](sourcebuffer) objects in the list.

### Event handlers

<span class="page-not-created">`SourceBufferList.onaddsourcebuffer`</span>  
The event handler for the `addsourcebuffer` event.

<span class="page-not-created">`SourceBufferList.onremovesourcebuffer`</span>  
The event handler for the `removesourcebuffer` event.

Methods
-------

*Inherits methods from its parent interface, [`EventTarget`](eventtarget).*

[`SourceBufferList`: indexed property getter](sourcebufferlist/sourcebuffer)  
This getter allows the `SourceBuffer` objects in the list to be accessed with an array operator (i.e. `[]`.)

Examples
--------

TBD.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#sourcebufferlist">Media Source Extensions<br />
<span class="small">The definition of 'SourceBufferList' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`SourceBufferList`

31

23-31

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

`length`

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

`onaddsourcebuffer`

53

17

42

11

Only works on Windows 8+.

40

8

53

53

No

41

No

6.0

`onremovesourcebuffer`

53

17

42

11

Only works on Windows 8+.

40

8

53

53

No

41

No

6.0

See also
--------

-   [`MediaSource`](mediasource)
-   [`SourceBuffer`](sourcebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBufferList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBufferList</a>
