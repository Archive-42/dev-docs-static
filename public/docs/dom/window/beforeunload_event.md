Window: beforeunload event
==========================

The `beforeunload` event is fired when the window, the document and its resources are about to be unloaded. The document is still visible and the event is still cancelable at this point.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../windoweventhandlers/onbeforeunload"><code>onbeforeunload</code></a></td></tr></tbody></table>

This event enables a web page to trigger a confirmation dialog asking the user if they really want to leave the page. If the user confirms, the browser navigates to the new page, otherwise it cancels the navigation.

According to the specification, to show the confirmation dialog an event handler should call [`preventDefault()`](../event/preventdefault) on the event.

However note that not all browsers support this method, and some instead require the event handler to implement one of two legacy methods:

-   assigning a string to the event's `returnValue` property
-   returning a string from the event handler.

Some browsers used to display the returned string in the confirmation dialog, enabling the event handler to display a custom message to the user. However, this is deprecated and no longer supported in most browsers.

To combat unwanted pop-ups, browsers may not display prompts created in `beforeunload` event handlers unless the page has been interacted with, or may even not display them at all.

The HTML specification states that calls to [`window.alert()`](alert), [`window.confirm()`](confirm), and [`window.prompt()`](prompt) methods may be ignored during this event. See the [HTML specification](https://html.spec.whatwg.org/multipage/timers-and-user-prompts.html#user-prompts) for more details.

Usage notes
-----------

The `beforeunload` event suffers from the same problems as the [`unload`](unload_event) event.

Especially on mobile, the `beforeunload` event is not reliably fired. For example, the `beforeunload` event is not fired at all in the following scenario:

1.  A mobile user visits your page.
2.  The user then switches to a different app.
3.  Later, the user closes the browser from the app manager.

The `beforeunload` event is not compatible with the [back/forward cache](https://web.dev/bfcache/) (bfcache), because many pages using this event assume that the page will not continue to exist after the event is fired. To combat this, browsers will not place pages in the bfcache if they have `beforeunload` listeners, and this is bad for performance.

However, unlike the `unload` event, there is a legitimate use case for the `beforeunload` event: the scenario where the user has entered unsaved data that will be lost if the page is unloaded.

It is recommended that developers listen for `beforeunload` only in this scenario, and only when they actually have unsaved changes, so as to minimize the effect on performance. See the Examples section below for an example of this.

See the [Page Lifecycle API](https://developers.google.com/web/updates/2018/07/page-lifecycle-api#the-beforeunload-event) guide for more information about the problems associated with the `beforeunload` event.

Examples
--------

In this example a page listens for changes to a [text `input`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/text). If the element contains a value, it adds a listener for `beforeunload`. If the element is empty, it removes the listener:

    const beforeUnloadListener = (event) => {
      event.preventDefault();
      return event.returnValue = "Are you sure you want to exit?";
    };

    const nameInput = document.querySelector("#name");

    nameInput.addEventListener("input", (event) => {
      if (event.target.value !== "") {
        addEventListener("beforeunload", beforeUnloadListener, {capture: true});
      } else {
        removeEventListener("beforeunload", beforeUnloadListener, {capture: true});
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-beforeunload">HTML Living Standard<br />
<span class="small">The definition of 'beforeunload' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#unloading-documents">HTML5<br />
<span class="small">The definition of 'beforeunload' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`beforeunload_event`

1

12

1

4

12

3

1

18

4

12

1

1.0

`custom_text_support`

Yes-51

No

Yes-44

Yes

Yes-38

Yes-9

Yes-51

Yes-51

Yes-44

Yes-41

No

Yes-5.0

`event_returnvalue_activation`

30

12

Yes

Yes

?

?

Yes

Yes

Yes

Yes

No

Yes

`preventdefault_activation`

No

12-79

Yes

9

No

11

No

No

Yes

No

No

No

`return_string_activation`

1

12

1

Yes

12

3

Yes

Yes

Yes

Yes

No

Yes

See [WindowEventHandlers/onbeforeunload](../windoweventhandlers/onbeforeunload#browser_compatibility) for more details on how various browsers handle this event.

See also
--------

-   Related events: [`DOMContentLoaded`](domcontentloaded_event), [`readystatechange`](../document/readystatechange_event), [`load`](load_event), [`unload`](unload_event)
-   [Unloading Documents — Prompt to unload a document](https://html.spec.whatwg.org/#prompt-to-unload-a-document)
-   [Remove Custom Messages in onbeforeload Dialogs after Chrome 51](https://developers.google.com/web/updates/2016/04/chrome-51-deprecations?hl=en#remove_custom_messages_in_onbeforeunload_dialogs)
-   [Don't lose user and app state, use Page Visibility](https://www.igvita.com/2015/11/20/dont-lose-user-and-app-state-use-page-visibility/) explains in detail why you should use `visibilitychange`, not `beforeunload`/`unload`.
-   [Page Lifecycle API](https://developers.google.com/web/updates/2018/07/page-lifecycle-api#developer-recommendations-for-each-state) gives best-practices guidance on handling page lifecyle behavior in your web applications.
-   [PageLifecycle.js](https://github.com/GoogleChromeLabs/page-lifecycle): a JavaScript library that deals with cross-browser inconsistencies in page lifecyle behavior.
-   [Back/forward cache](https://web.dev/bfcache/) explains what the back/forward cache is, and its implications for various page lifecycle events.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/beforeunload_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/beforeunload_event</a>
