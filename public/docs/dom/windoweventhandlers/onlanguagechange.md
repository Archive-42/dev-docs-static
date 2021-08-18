WindowEventHandlers.onlanguagechange
====================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onlanguagechange` property of the [`WindowEventHandlers`](../windoweventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `languagechange` events.

These events are received by the object implementing this interface, usually a [`Window`](../window), an [`HTMLBodyElement`](../htmlbodyelement), or an [`HTMLIFrameElement`](../htmliframeelement). Such an event is sent by the browser to inform that the preferred languages list has been updated. The list is accessible via [`NavigatorLanguage.languages`](../navigatorlanguage/languages).

Syntax
------

    object.onlanguagechange = function;

### Value

-   `function` is the name of a user-defined function, without the `()` suffix or any parameters, or an anonymous function declaration, such as `function(event) {...}`. An event handler always has one single parameter, containing the event, here of type [`Event`](../event).

Example
-------

    window.onlanguagechange = function(event) {
      console.log('languagechange event detected!');
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-window-onlanguagechange">HTML Living Standard<br />
<span class="small">The definition of 'WindowEventHandler.onlanguagechange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onlanguagechange`

37

≤79

32

No

24

?

37

37

4

24

?

4.0

See also
--------

-   The `languagechange` event and its type, [`Event`](../event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onlanguagechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onlanguagechange</a>
