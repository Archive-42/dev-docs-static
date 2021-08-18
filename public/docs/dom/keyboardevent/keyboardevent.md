KeyboardEvent()
===============

The `KeyboardEvent()` constructor creates a new [`KeyboardEvent`](../keyboardevent).

Syntax
------

     event = new KeyboardEvent(typeArg, KeyboardEventInit);

### Values

*typeArg*  
Is a [`DOMString`](../domstring) representing the name of the event.

 *KeyboardEventInit*<span class="badge inline optional">Optional</span>   
Is a `KeyboardEventInit` dictionary, having the following fields:

-   `"key"`, optional and defaulting to `""`, of type [`DOMString`](../domstring), that sets the value of [`KeyboardEvent.key`](key).
-   `"code"`, optional and defaulting to `""`, of type [`DOMString`](../domstring), that sets the value of [`KeyboardEvent.code`](code).
-   `"location"`, optional and defaulting to `0`, of type `unsigned long`, that sets the value of [`KeyboardEvent.location`](location).
-   `"ctrlKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that sets the value of [`KeyboardEvent.ctrlKey`](ctrlkey).
-   `"shiftKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that sets the value of [`KeyboardEvent.shiftKey`](shiftkey).
-   `"altKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that sets the value of [`KeyboardEvent.altKey`](altkey).
-   `"metaKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that sets the value of [`KeyboardEvent.metaKey`](metakey).
-   `"repeat"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that sets the value of [`KeyboardEvent.repeat`](repeat).
-   `"isComposing"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that sets the value of [`KeyboardEvent.isComposing`](iscomposing).
-   `"charCode"`, optional and defaulting to `0`, of type `unsigned long`, that sets the value of the deprecated [`KeyboardEvent.charCode`](charcode).
-   `"keyCode"`, optional and defaulting to `0`, of type `unsigned long`, that sets the value of the deprecated [`KeyboardEvent.keyCode`](keycode).
-   `"which"`, optional and defaulting to `0`, of type `unsigned long`, that sets the value of the deprecated [`KeyboardEvent.which`](which).

*The `KeyboardEventInit` dictionary also accepts fields from the [`UIEventInit`](../uievent/uievent) and [`EventInit`](../event/event) dictionaries.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#dom-keyboardevent-keyboardevent">UI Events<br />
<span class="small">The definition of 'KeyboardEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#interface-KeyboardEvent">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'KeyboardEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`KeyboardEvent`

Yes

≤79

31

No

Yes

Yes

Yes

Yes

31

Yes

Yes

Yes

`code_and_key_in_init`

49

≤79

?

No

?

?

49

49

?

?

?

5.0

See also
--------

-   [`KeyboardEvent`](../keyboardevent), the interface of the objects it constructs.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/KeyboardEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/KeyboardEvent</a>
