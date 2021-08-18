# GlobalEventHandlers.oncanplay

The `oncanplay` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `canplay` events.

The `canplay` event is fired when the user agent can play the media, but estimates that not enough data has been loaded to play the media up to its end without having to stop for further buffering of content.

## Syntax

    element.oncanplay = handlerFunction;
    var handlerFunction = element.oncanplay;

`handlerFunction` is either `null` or a [JavaScript function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions) specifying the handler for the event.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-oncanplay">HTML Living Standard<br />
<span class="small">The definition of 'oncanplay' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`oncanplay`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

## See also

- [DOM event handlers](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplay" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncanplay</a>
