# Document.onvisibilitychange

The `Document.onvisibilitychange` property represents the event handler that is called when a `visibilitychange` event reaches this object.

Safari doesn’t fire the `visibilitychange` event as expected when `visibilityState` transitions to `hidden`; so for that case, you need to also include code to listen for the `pagehide` event.

## Syntax

    obj.onvisibilitychange = function;

- `function` is the name of a user-defined function, without the () suffix or any parameters, or an anonymous function declaration.

## Example

    document.onvisibilitychange = function() {
      console.log("Visibility of page has changed!");
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/page-visibility/#dom-document-onvisibilitychange">Page Visibility (Second Edition)<br />
<span class="small">The definition of 'onvisibilitychange' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onvisibilitychange`

62

Before Chrome 62, this event handler attribute is not supported; however, the event itself is supported since Chrome 33. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

18

Before Edge 18, this event handler attribute was not supported; however, the event itself was supported since Edge 12. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

56

No

This event handler attribute is not supported; however, the event itself is supported since IE 10. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

49

Before Opera 49, this event handler attribute is not supported; however, the event itself is supported since Opera 20. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

10.1

\["Doesn't fire the `visibilitychange` event when navigating away from a document, so also include code to check for the `pagehide` event (which does fire for that case in all current browsers). See WebKit bugs [116769](https://webkit.org/b/116769), [151234](https://webkit.org/b/151234), [151610](https://webkit.org/b/151610), and [194897](https://webkit.org/b/194897).", "Before Safari 10.1, this event handler attribute was not supported; however, the event itself was supported since Safari 7. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`."\]

62

Before WebView 62, this event handler attribute is not supported; however, the event itself is supported since WebView 4.4.3. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

62

Before Chrome 62, this event handler attribute is not supported; however, the event itself is supported since Chrome 33. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

56

46

Before Opera Android 46, this event handler attribute is not supported; however, the event itself is supported since Opera Android 20. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

10.3

\["Doesn't fire the `visibilitychange` event when navigating away from a document, so also include code to check for the `pagehide` event (which does fire for that case in all current browsers). See WebKit bugs [116769](https://webkit.org/b/116769), [151234](https://webkit.org/b/151234), [151610](https://webkit.org/b/151610), and [194897](https://webkit.org/b/194897).", "Before Safari iOS 10.3, this event handler attribute was not supported; however, the event itself was supported since Safari iOS 7. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`."\]

8.0

Before Samsung Internet 8.0, this event handler attribute is not supported; however, the event itself is supported since Samsung Internet 2.0. The event can be listened to via `document.addEventListener('visibilitychange', function() {});`.

## See also

- [Page Visibility API](../page_visibility_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/onvisibilitychange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/onvisibilitychange</a>
