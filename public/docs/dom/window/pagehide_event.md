Window: pagehide event
======================

The `pagehide` event is sent to a [`Window`](../window) when the browser hides the current page in the process of presenting a different page from the session's history. For example, when the user clicks the browser's Back button, the current page receives a `pagehide` event before the previous page is shown.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../pagetransitionevent"><code>PageTransitionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>onpagehide</code></span></td></tr></tbody></table>

Usage notes
-----------

Like the [`unload`](unload_event) and [`beforeunload`](beforeunload_event) events, this event is not reliably fired by browsers, especially on mobile. For example, the `pagehide` event is not fired at all in the following scenario:

1.  A mobile user visits your page.
2.  The user then switches to a different app.
3.  Later, the user closes the browser from the app manager.

However, unlike the `unload` and `beforeunload` events, this event is compatible with the [back/forward cache](https://web.dev/bfcache/) (bfcache), so adding a listener to this event will not prevent the page from being included in the bfcache.

The best event to use to signal the end of a user's session is the [`visibilitychange`](../document/visibilitychange_event) event. In browsers that don't support `visibilitychange` the `pagehide` event is the next-best alternative.

If you're specifically trying to detect page unload events, the `pagehide` event is the best option.

See the [Page Lifecycle API](https://developers.google.com/web/updates/2018/07/page-lifecycle-api) guide for more information about how this event relates to other events in the page lifecycle.

Examples
--------

In this example, an event handler is established to watch for `pagehide` events and to perform special handling if the page is being persisted for possible reuse.

    window.addEventListener("pagehide", event => {
      if (event.persisted) {
        /* the page isn't being discarded, so it can be reused later */
      }
    }, false);

This can also be written using the <span class="page-not-created">`onpagehide`</span> event handler property on the [`Window`](../window):

    window.onpagehide = event => {
      if (event.persisted) {
        /* the page isn't being discarded, so it can be reused later */
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsing-the-web.html#event-pagehide">HTML Living Standard<br />
<span class="small">The definition of 'pagehide' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial specification.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#event-pagehide">HTML5<br />
<span class="small">The definition of 'pagehide' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`pagehide_event`

3

12

Yes

Yes

Yes

Yes

≤37

18

Yes

Yes

Yes

1.0

See also
--------

-   The [`pageshow`](pageshow_event) event.
-   [Page Lifecycle API](https://developers.google.com/web/updates/2018/07/page-lifecycle-api#developer-recommendations-for-each-state) gives best-practices guidance on handling page lifecyle behavior in your web applications.
-   [PageLifecycle.js](https://github.com/GoogleChromeLabs/page-lifecycle): a JavaScript library that deals with cross-browser inconsistencies in page lifecyle behavior.
-   [Back/forward cache](https://web.dev/bfcache/) explains what the back/forward cache is, and its implications for various page lifecycle events.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/pagehide_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/pagehide_event</a>
