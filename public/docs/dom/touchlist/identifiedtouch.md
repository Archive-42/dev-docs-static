TouchList.identifiedTouch()
===========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `identifiedTouch()` method returns the first [`Touch`](../touch) item in the [`TouchList`](../touchlist) that matches the specified identifier.

It is recommended that you use [`TouchList.item()`](item) instead.

Syntax
------

    var touchItem = touchList.identifiedTouch(id);

### Parameters

`id`  
An integer value identifying the [`Touch`](../touch) object to retrieve from the list.

### Return value

`touchItem`  
A [`Touch`](../touch) object matching the specified `id`.

Specifications
--------------

Not part of any specification. This API was removed from the Touch Events v2 draft specification.

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

`identifiedTouch`

?

?

?

No

?

No

?

?

?

?

?

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TouchList/identifiedTouch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TouchList/identifiedTouch</a>