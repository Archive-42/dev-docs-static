# GlobalEventHandlers.onmousewheel

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The **onmousewheel** property sets and returns the [event handler](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for the `mousewheel` event.

**Do not use this wheel event.** This interface is non-standard and deprecated. It was used in non-Gecko browsers only. Instead use the standard `wheel` event.

## Syntax

    element.onmousewheel = handlerFunction;
    var handlerFunction = element.onmousewheel;

`handlerFunction` should be either `null` or a [JavaScript function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions) specifying the handler for the event.

## Notes

See the [DOM event handlers](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) page for information on working with `on...` handlers.

The `mousewheel` event is fired asynchronously when a mouse wheel or similar device is operated. It's represented by the [`MouseWheelEvent`](../mousewheelevent) interface.

See the `mousewheel` event documentation for more information about the event.

## Browser compatibility

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

`onmousewheel`

Yes

≤79

No

?

?

?

Yes

Yes

No

?

?

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousewheel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousewheel</a>
