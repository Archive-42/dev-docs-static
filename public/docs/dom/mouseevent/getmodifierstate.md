MouseEvent.getModifierState()
=============================

The `MouseEvent.getModifierState()` method returns the current state of the specified modifier key: `true` if the modifier is active (i.e., the modifier key is pressed or locked), otherwise, `false`.

See the document of [`KeyboardEvent.getModifierState()`](../keyboardevent/getmodifierstate) for details.

Syntax
------

    var active = event.getModifierState(keyArg);

### Returns

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

### Parameters

*`keyArg`*  
A modifier key value. The value must be one of the [`KeyboardEvent.key`](../keyboardevent/key) values which represent modifier keys or `"Accel"`<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>. This is case-sensitive.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-MouseEvent-getModifierState">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'getModifierState()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getModifierState`

47

12

Yes

?

Yes

12.1

47

47

Yes

Yes

12.2

5.0

`accel_support`

No

No

?

?

?

?

No

No

?

?

?

No

See also
--------

-   The [`MouseEvent`](../mouseevent) this method belongs to.
-   [`KeyboardEvent.getModifierState`](../keyboardevent/getmodifierstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/getModifierState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/getModifierState</a>
