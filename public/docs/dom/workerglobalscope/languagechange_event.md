WorkerGlobalScope: languagechange event
=======================================

The `languagechange` event is fired at the global scope object when the user's preferred language changes.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler</td><td><a href="onlanguagechange"><code>onlanguagechange</code></a></td></tr></tbody></table>

Examples
--------

You can use the `languagechange` event in an [`addEventListener`](../eventtarget/addeventlistener) method:

    worker.addEventListener('languagechange', function() {
      console.log('languagechange event detected!');
    });

Or use the [`onlanguagechange`](onlanguagechange) event handler property:

    worker.onlanguagechange = function(event) {
      console.log('languagechange event detected!');
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#event-languagechange">HTML Living Standard<br />
<span class="small">The definition of 'languagechange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`languagechange_event`

4

12

74

Yes

11.5

4

≤37

40

No

Yes

5.1

4.0

See also
--------

-   [`navigator.language`](../navigatorlanguage/language)
-   [`navigator.languages`](../navigatorlanguage/languages)
-   [`Navigator`](../navigator)
-   [`WorkerGlobalScope.onlanguagechange`](onlanguagechange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/languagechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/languagechange_event</a>
