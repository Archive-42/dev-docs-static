Event.returnValue
=================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`Event`](../event) property `returnValue` indicates whether the default action for this event has been prevented or not. It is set to `true` by default, allowing the default action to occur. Setting this property to `false` prevents the default action.

**Note**

While `returnValue` has been adopted into the DOM standard, it is present primarily to support existing code. You should use [`preventDefault()`](preventdefault), and [`defaultPrevented`](defaultprevented) instead of this historical property.

Syntax
------

    event.returnValue = bool;

    var bool = event.returnValue;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value which is `true` if the event has not been canceled; otherwise, if the event has been canceled or the default has been prevented, the value is `false`.

The value returned by `returnValue` is the opposite of the value returned by [`defaultPrevented`](defaultprevented).

Usage notes
-----------

`returnValue` was introduced into the DOM by Internet Explorer 6, and due to that browser's ubiquity became so commonly used that other browsers eventually implemented it as well. It has been adopted into the DOM specification, primarily to ensure that existing web content continues to function going forward.

New projects should generally avoid using `returnValue`, although they may if they choose to do so.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-returnvalue">DOM<br />
<span class="small">The definition of 'returnValue' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added for legacy compatibility.</td></tr></tbody></table>

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

`returnValue`

Yes

12

No

Temporarily added in 63, removed in 64, briefly added in 65, then removed again while related compatibility issues are sorted out (see [bug 1520756](https://bugzil.la/1520756)).

6

Yes

Yes

Yes

Yes

No

Temporarily added in 63, removed in 64, briefly added in 65, then removed again while related compatibility issues are sorted out (see [bug 1520756](https://bugzil.la/1520756)).

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/returnValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/returnValue</a>
