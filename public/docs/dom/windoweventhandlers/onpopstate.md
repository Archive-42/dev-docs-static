WindowEventHandlers.onpopstate
==============================

The `onpopstate` property of the [`WindowEventHandlers`](../windoweventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `popstate` events on the window.

A `popstate` event is dispatched to the window each time the active history entry changes between two history entries for the same document. If the activated history entry was created by a call to `history.pushState()`, or was affected by a call to `history.replaceState()`, the `popstate` event's `state` property contains a copy of the history entry's state object.

**Note**: Calling `history.pushState()` or `history.replaceState()` won't trigger a `popstate` event. The `popstate` event is only triggered by performing a browser action, such as clicking on the back button (or calling `history.back()` in JavaScript), when navigating between two history entries for the same document.

Syntax
------

    window.onpopstate = funcRef;

-   `funcRef` is a handler function.

Examples
--------

For example, a page at `http://example.com/example.html` running the following code will generate alerts as indicated:

    window.onpopstate = function(event) {
      alert("location: " + document.location + ", state: " + JSON.stringify(event.state));
    };

    history.pushState({page: 1}, "title 1", "?page=1");
    history.pushState({page: 2}, "title 2", "?page=2");
    history.replaceState({page: 3}, "title 3", "?page=3");
    history.back(); // alerts "location: http://example.com/example.html?page=1, state: {"page":1}"
    history.back(); // alerts "location: http://example.com/example.html, state: null
    history.go(2);  // alerts "location: http://example.com/example.html?page=3, state: {"page":3}

Note that even though the original history entry (for `http://example.com/example.html`) has no state object associated with it, a `popstate` event is still fired, when we activate that entry after the second call to `history.back()`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-window-onpopstate">HTML Living Standard<br />
<span class="small">The definition of 'onpopstate' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onpopstate`

5

12

4

10

11.5

6

37

18

4

11.5

5.1

1.0

See also
--------

-   [`window.history`](../window/history)
-   [Manipulating the browser history](../history_api)
-   [Ajax navigation example](../history_api/example)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onpopstate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onpopstate</a>
