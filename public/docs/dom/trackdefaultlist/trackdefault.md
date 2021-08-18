TrackDefaultList.TrackDefault()
===============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `TrackDefault()` getter method of the [`TrackDefaultList`](../trackdefaultlist) interface allows the `TrackDefault` objects in the list to be accessed with an array operator (i.e. `[]`.)

Syntax
------

    var myTrackDefault = TrackDefaultList[index];

### Parameters

index  
The index position of the [`TrackDefault`](../trackdefault) object you want to return.

### Returns

A [`TrackDefault`](../trackdefault) object.

### Errors

No specific errors are returned, but if the supplied index is great than or equal to [`TrackDefaultList.length`](length), the operation will return `undefined`.

Example
-------

TBD.

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
-   [`TrackDefaultList`](../trackdefaultlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrackDefaultList/TrackDefault" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrackDefaultList/TrackDefault</a>
