PageTransitionEvent
===================

The `PageTransitionEvent` event object is available inside handler functions for the `pageshow` and `pagehide` events, fired when a document is being loaded or unloaded.

Properties
----------

*This interface also inherits properties from its parent, [`Event`](event).*

 [`PageTransitionEvent.persisted`](pagetransitionevent/persisted) <span class="badge inline readonly">Read only </span>   
Indicates if the document is loading from a cache.

Example
-------

### HTML

    <!DOCTYPE html>
    <html>
    <body>
    </body>
    </html>

### JavaScript

    window.addEventListener('pageshow', myFunction);

    function myFunction(event) {
      if (event.persisted) {
        alert("The page was cached by the browser");
      } else {
        alert("The page was NOT cached by the browser");
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#the-pagetransitionevent-interface">HTML Living Standard<br />
<span class="small">The definition of 'PageTransitionEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`PageTransitionEvent`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`persisted`

Yes

12

Yes

11

The `persisted` property is known to be buggy in Internet Explorer. It is advised to check if `window.performance.navigation.type == 2` as well.

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`pageshow` event](window/pageshow_event)
-   [`pagehide` event](window/pagehide_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PageTransitionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PageTransitionEvent</a>
