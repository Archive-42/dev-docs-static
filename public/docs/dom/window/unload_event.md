Window: unload event
====================

Developers should avoid using this event. See "Usage notes" below.

The `unload` event is fired when the document or a child resource is being unloaded.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../windoweventhandlers/onunload"><code>onunload</code></a></td></tr></tbody></table>

It is fired after:

-   [`beforeunload`](beforeunload_event) (cancelable event)
-   [`pagehide`](pagehide_event)

The document is in the following state:

-   All the resources still exist (img, iframe etc.)
-   Nothing is visible anymore to the end user
-   UI interactions are ineffective ([`window.open`](open), [`alert`](alert), [`confirm`](confirm), etc.)
-   An error won't stop the unloading workflow

Please note that the unload event also follows the document tree: parent frame unload will happen **before** child frame `unload` (see example below).

Usage notes
-----------

Developers should avoid using this event.

Especially on mobile, the `unload` event is not reliably fired. For example, the `unload` event is not fired at all in the following scenario:

1.  A mobile user visits your page.
2.  The user then switches to a different app.
3.  Later, the user closes the browser from the app manager.

Also, the `unload` event is not compatible with the [back/forward cache](https://web.dev/bfcache/) (bfcache), because many pages using this event assume that the page will not continue to exist after the event is fired. To combat this, some browsers (such as Firefox) will not place pages in the bfcache if they have unload listeners, and this is bad for performance. Others, such as Chrome, will not fire the `unload` when a user navigates away.

The best event to use to signal the end of a user's session is the [`visibilitychange`](../document/visibilitychange_event) event. In browsers that don't support `visibilitychange` the next-best alternative is the [`pagehide`](pagehide_event) event, which is also not fired reliably, but which is bfcache-compatible.

If you're specifically trying to detect page unload events, it's best to listen for the `pagehide` event.

See the [Page Lifecycle API](https://developers.google.com/web/updates/2018/07/page-lifecycle-api#the-unload-event) guide for more information about the problems associated with the `unload` event.

Examples
--------

    <!DOCTYPE html>
    <html>
      <head>
        <title>Parent Frame</title>
        <script>
          window.addEventListener('beforeunload', function(event) {
            console.log('I am the 1st one.');
          });
          window.addEventListener('unload', function(event) {
            console.log('I am the 3rd one.');
          });
        </script>
      </head>
      <body>
        <iframe src="child-frame.html"></iframe>
      </body>
    </html>

Below, the content of `child-frame.html`:

    <!DOCTYPE html>
    <html>
      <head>
        <title>Child Frame</title>
        <script>
          window.addEventListener('beforeunload', function(event) {
            console.log('I am the 2nd one.');
          });
          window.addEventListener('unload', function(event) {
            console.log('I am the 4th and last one…');
          });
        </script>
      </head>
      <body>
          ☻
      </body>
    </html>

When the parent frame is unloaded, events will be fired in the order described by the `console.log()` messages.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#event-unload">HTML Living Standard<br />
<span class="small">The definition of 'unload' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`unload_event`

1

12

1

4

4

3

1

18

4

10.1

1

1.0

See also
--------

-   Related events: [`DOMContentLoaded`](domcontentloaded_event), [`readystatechange`](../document/readystatechange_event), [`load`](load_event)
-   [Unloading Documents — unload a document](https://html.spec.whatwg.org/multipage/browsers.html#unloading-documents)
-   The [`visibilitychange`](../document/visibilitychange_event) event.
-   [Don't lose user and app state, use Page Visibility](https://www.igvita.com/2015/11/20/dont-lose-user-and-app-state-use-page-visibility/) explains in detail why you should use `visibilitychange`, not `beforeunload`/`unload`.
-   [Page Lifecycle API](https://developers.google.com/web/updates/2018/07/page-lifecycle-api#developer-recommendations-for-each-state) gives best-practices guidance on handling page lifecyle behavior in your web applications.
-   [PageLifecycle.js](https://github.com/GoogleChromeLabs/page-lifecycle): a JavaScript library that deals with cross-browser inconsistencies in page lifecyle behavior.
-   [Back/forward cache](https://web.dev/bfcache/) explains what the back/forward cache is, and its implications for various page lifecycle events.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/unload_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/unload_event</a>
