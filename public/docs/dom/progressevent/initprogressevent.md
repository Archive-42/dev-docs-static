ProgressEvent.initProgressEvent()
=================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `ProgressEvent.initProgressEvent()` method Initializes an animation event created using the deprecated [`Document.createEvent("ProgressEvent")`](../document/createevent) method.

`ProgressEvent` created that way are untrusted.

**Note:** this method has been dropped during the standard process. It has been deprecated and removed from most implementation. Do not use it anymore, use the standard constructor, [`ProgressEvent()`](progressevent), to create a synthetic [`ProgressEvent`](../progressevent)

Syntax
------

    Progress.initProgressEvent(typeArg, canBubbleArg, cancelableArg, lengthComputable, loaded, total);

### Parameters

*typeArg*  
Is a [`DOMString`](../domstring) identifying the specific type of animation event that occurred. The following values are allowed:

<table><thead><tr class="header"><th>Value</th><th>Meaning</th></tr></thead><tbody><tr class="odd"><td><code>loadstart</code></td><td>The operation has started.</td></tr><tr class="even"><td><code>progress</code></td><td>The operation still is in progress.</td></tr><tr class="odd"><td><code>error</code></td><td>The operation failed and didn't complete.</td></tr><tr class="even"><td><code>abort</code></td><td>The operation was cancelled and didn't complete.</td></tr><tr class="odd"><td><code>load</code></td><td>The operation completed.</td></tr><tr class="even"><td><code>loadend</code></td><td>The operation stopped.</td></tr></tbody></table>

*canBubbleArg*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the event can bubble (`true`) or not (`false)`.

*cancelableArg*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the event associated action can be avoided (`true`) or not (`false)`.

*lengthComputable*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the total work to be done, and the amount of work already done, by the underlying process is calculable. In other words, it tells if the progress is measurable or not.

*loaded*  
Is an `unsigned long long` representing the amount of work already performed by the underlying process. The ratio of work done can be calculated with the property and `ProgressEvent.total`. When downloading a resource using HTTP, this only represent the part of the content itself, not headers and other overhead.

*total*  
Is an `unsigned long long` representing the total amount of work that the underlying process is in the progress of performing. When downloading a resource using HTTP, this only represent the content itself, not headers and other overhead.

Specifications
--------------

This feature does not exist in any specifications.

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

`initProgressEvent`

1-17

12-79

3.5-22

10

Yes-15

Yes-6

No

Yes-18

4-22

Yes-14

Yes-6

No

See also
--------

-   The [`ProgressEvent`](../progressevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent/initProgressEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent/initProgressEvent</a>
