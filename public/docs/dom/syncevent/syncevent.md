SyncEvent.SyncEvent()
=====================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `SyncEvent()` constructor creates a new [`SyncEvent`](../syncevent) object.

Syntax
------

    var mySyncEvent = new SyncEvent(type, init)

### Parameters

*type*  
The type of the Event.

 *init* <span class="badge inline optional">Optional</span>   
An options object containing any custom settings that you want to apply to the event object. Options are as follows:

-   `tag`: A developer-defined unique identifier for this `SyncEvent`.
-   `lastChance`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating that the user agent will not make further synchronization attempts after the current attempt.

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SyncEvent/SyncEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SyncEvent/SyncEvent</a>
