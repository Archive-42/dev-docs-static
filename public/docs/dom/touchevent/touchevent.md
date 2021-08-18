TouchEvent()
============

The `Event()` constructor creates a new [`TouchEvent`](../touchevent).

Syntax
------

     event = new TouchEvent(typeArg, touchEventInit);

### Values

*typeArg*  
Is a [`DOMString`](../domstring) representing the name of the event.

 *touchEventInit* <span class="badge inline optional">Optional</span>   
Is a Touch`EventInit` dictionary, having the following fields:

-   `"touches"`, optional and defaulting to `[]`, of type `Touch[]`, that is a list of objects for every point of contact currently touching the surface.
-   `"targetTouches"`, optional and defaulting to `[]`, of type `Touch[]`, that is a list of objects for every point of contact that is touching the surface *and* started on the element that is the target of the current event.
-   `"changedTouches"`, optional and defaulting to `[]`, of type `Touch[]`, that is a list of objects for every point of contact which contributed to the event.
-   `"ctrlKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that indicates if the ctrl key was simultaneously pressed.
-   `"shiftKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that indicates if the shift key was simultaneously pressed.
-   `"altKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that indicates if the alt key was simultaneously pressed.
-   `"metaKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that indicates if the meta key was simultaneously pressed.

*The Touch`EventInit` dictionary also accepts fields from [`UIEventInit`](../uievent/uievent) and from [`EventInit`](../event/event) dictionaries.*

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

`TouchEvent`

48

Chrome only supports the following `touchEventInit` properties: `touches`, `targetTouches`, `changedTouches`.

≤79

Edge only supports the following `touchEventInit` properties: `touches`, `targetTouches`, `changedTouches`.

?

No

Yes

No

48

Chrome only supports the following `touchEventInit` properties: `touches`, `targetTouches`, `changedTouches`.

48

Chrome only supports the following `touchEventInit` properties: `touches`, `targetTouches`, `changedTouches`.

Yes

Yes

3.2

5.0

Samsung Internet only supports the following `touchEventInit` properties: `touches`, `targetTouches`, `changedTouches`.

See also
--------

-   [`TouchEvent`](../touchevent), the interface of the objects it constructs.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/TouchEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/TouchEvent</a>
