SyncEvent
=========

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `SyncEvent` interface represents a sync action that is dispatched on the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) of a ServiceWorker.

This interface inherits from the [`ExtendableEvent`](extendableevent) interface.

Constructor
-----------

[`SyncEvent.SyncEvent()`](syncevent/syncevent)  
Creates a new `SyncEvent` object.

Properties
----------

*Inherits properties from its ancestor, [`Event`](event)*.

 [`SyncEvent.tag`](syncevent/tag) <span class="badge inline readonly">Read only </span>   
Returns the developer-defined identifier for this `SyncEvent`.

 [`SyncEvent.lastChance`](syncevent/lastchance) <span class="badge inline readonly">Read only </span>   
Returns `true` if the user agent will not make further synchronization attempts after the current attempt.

Methods
-------

*Inherits methods from its parent, [`ExtendableEvent`](extendableevent)*.

None.

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

`SyncEvent`

49

≤79

?

No

?

?

No

49

?

?

?

5.0

`SyncEvent`

49

≤79

?

No

?

?

No

49

?

?

?

5.0

`lastChance`

49

≤79

?

No

?

?

No

49

?

?

?

5.0

`tag`

49

≤79

?

No

?

?

No

49

?

?

?

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SyncEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SyncEvent</a>
