# Document: visibilitychange event

The `visibilitychange` event is fired at the document when the contents of its tab have become visible or have been hidden.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onvisibilitychange"><code>onvisibilitychange</code></a></td></tr></tbody></table>

## Usage notes

The event doesn't include the document's updated visibility status, but you can get that information from the document's [`visibilityState`](visibilitystate) property.

This event fires with a `visibilityState` of `hidden` when a user navigates to a new page, switches tabs, closes the tab, minimizes or closes the browser, or, on mobile, switches from the browser to a different app. Transitioning to `hidden` is the last event that's reliably observable by the page, so developers should treat it as the likely end of the user's session (for example, for [sending analytics data](../navigator/sendbeacon)).

The transition to `hidden` is also a good point at which pages can stop making UI updates and stop any tasks that the user doesn't want to have running in the background.

## Examples

### Pausing music on transitioning to hidden

This example begins playing a music track when the document becomes visible, and pauses the music when the document is no longer visible.

    document.addEventListener("visibilitychange", function() {
      if (document.visibilityState === 'visible') {
        backgroundMusic.play();
      } else {
        backgroundMusic.pause();
      }
    });

### Sending end-of-session analytics on transitioning to hidden

This example treats the transition to `hidden` as the end of the user's session, and sends the appropriate analytics using the [`Navigator.sendBeacon()`](../navigator/sendbeacon) API:

    document.addEventListener('visibilitychange', function logData() {
      if (document.visibilityState === 'hidden') {
        navigator.sendBeacon('/log', analyticsData);
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/page-visibility/#dfn-visibilitychange">Page Visibility (Second Edition)<br />
<span class="small">The definition of 'visibilitychange' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`visibilitychange_event`

33

Before Chrome 62, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Chrome, use `document.addEventListener('visibilitychange', function() {});`.

13

12

Before Edge 18, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Edge, use `document.addEventListener('visibilitychange', function() {});`.

56

10

The `onvisibilitychange` attribute is not supported in IE. To listen to this event, use `document.addEventListener('visibilitychange', function() {});`.

20

Before Opera 49, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Opera, use `document.addEventListener('visibilitychange', function() {});`.

15

12.1-15

7

\["Doesn't fire the `visibilitychange` event when navigating away from a document, so also include code to check for the `pagehide` event (which does fire for that case in all current browsers). See WebKit bugs [116769](https://webkit.org/b/116769), [151234](https://webkit.org/b/151234), [151610](https://webkit.org/b/151610), and [194897](https://webkit.org/b/194897).", "Before Safari 14, the event does not bubble, so `document.addEventListener('visibilitychange', ...)` works, but `window.addEventListener('visibilitychange', ...)` does not.", "Before Safari 10.1, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Safari, use `document.addEventListener('visibilitychange', function() {});`."\]

4.4.3

Before WebView 62, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of WebView, use `document.addEventListener('visibilitychange', function() {});`.

≤37

33

Before Chrome 62, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Chrome, use `document.addEventListener('visibilitychange', function() {});`.

18

56

20

Before Opera Android 46, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Opera Android, use `document.addEventListener('visibilitychange', function() {});`.

14

12.1-14

7

\["Doesn't fire the `visibilitychange` event when navigating away from a document, so also include code to check for the `pagehide` event (which does fire for that case in all current browsers). See WebKit bugs [116769](https://webkit.org/b/116769), [151234](https://webkit.org/b/151234), [151610](https://webkit.org/b/151610), and [194897](https://webkit.org/b/194897).", "Before Safari iOS 14, the event does not bubble, so `document.addEventListener('visibilitychange', ...)` works, but `window.addEventListener('visibilitychange', ...)` does not.", "Before Safari iOS 10.3, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Safari iOS, use `document.addEventListener('visibilitychange', function() {});`."\]

2.0

Before Samsung Internet 8.0, the `onvisibilitychange` attribute is not supported. To listen to this event in earlier versions of Samsung Internet, use `document.addEventListener('visibilitychange', function() {});`.

1.0

## See also

- [Page Visibility API](../page_visibility_api)
- [`Document.visibilityState`](visibilitystate)
- [Don't lose user and app state, use Page Visibility](https://www.igvita.com/2015/11/20/dont-lose-user-and-app-state-use-page-visibility/) explains in detail why you should use `visibilitychange`, not `beforeunload`/`unload`.
- [Page Lifecycle API](https://developers.google.com/web/updates/2018/07/page-lifecycle-api#developer-recommendations-for-each-state) gives best-practices guidance on handling page lifecyle behavior in your web applications.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/visibilitychange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/visibilitychange_event</a>
