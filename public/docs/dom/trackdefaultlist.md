TrackDefaultList
================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `TrackDefaultList` interface represents a simple container list for multiple [`TrackDefault`](trackdefault) objects.

The `TrackDefaultList` associated with a particular `SourceBuffer` can be retrieved using the [`SourceBuffer.trackDefaults`](sourcebuffer/trackdefaults) property.

Constructor
-----------

[`TrackDefaultList()`](trackdefaultlist/trackdefaultlist)  
Constructs and returns a new `TrackDefaultList` object.

Properties
----------

*Inherits properties from its parent interface, [`EventTarget`](eventtarget).*

 [`TrackDefaultList.length`](trackdefaultlist/length) <span class="badge inline readonly">Read only </span>   
Returns the number of [`TrackDefault`](trackdefault) objects in the list.

Methods
-------

*Inherits properties from its parent interface, [`EventTarget`](eventtarget).*

[`TrackDefaultList.TrackDefault()`](trackdefaultlist/trackdefault)  
This getter allows the `TrackDefault` objects in the list to be accessed with an array operator (i.e. `[]`.)

Examples
--------

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

`TrackDefaultList`

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

`TrackDefaultList`

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

`length`

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

-   [`MediaSource`](mediasource)
-   [`SourceBuffer`](sourcebuffer)
-   [`TrackDefaultList`](trackdefaultlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrackDefaultList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrackDefaultList</a>
