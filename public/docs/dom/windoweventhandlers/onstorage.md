WindowEventHandlers.onstorage
=============================

The `onstorage` property of the [`WindowEventHandlers`](../windoweventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `storage` events.

The `storage` event fires when a storage area has been changed in the context of another document.

Syntax
------

     window.onstorage = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). This function receives a [`StorageEvent`](../storageevent) as its sole argument.

Example
-------

This example logs the value for a storage key whenever it changes in another document.

    window.onstorage = function(e) {
      console.log('The ' + e.key +
        ' key has been changed from ' + e.oldValue +
        ' to ' + e.newValue + '.');
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-window-onstorage">HTML Living Standard<br />
<span class="small">The definition of 'onstorage' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onstorage`

1

≤18

45

?

15

?

≤37

18

45

14

?

1.0

See also
--------

-   [Window: `storage` event](../window/storage_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onstorage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onstorage</a>
