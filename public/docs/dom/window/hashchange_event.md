Window: hashchange event
========================

The `hashchange` event is fired when the fragment identifier of the URL has changed (the part of the URL beginning with and following the `#` symbol).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../hashchangeevent"><code>HashChangeEvent</code></a></td></tr><tr class="even"><td>Event handler</td><td><a href="../windoweventhandlers/onhashchange"><code>onhashchange</code></a></td></tr></tbody></table>

Examples
--------

You can use the `hashchange` event in an [`addEventListener`](../eventtarget/addeventlistener) method:

    window.addEventListener('hashchange', function() {
      console.log('The hash has changed!')
    }, false);

Or use the `onhashchange` event handler property:

    function locationHashChanged() {
      if (location.hash === '#cool-feature') {
        console.log("You're visiting a cool feature!");
      }
    }

    window.onhashchange = locationHashChanged;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-hashchange">HTML Living Standard<br />
<span class="small">The definition of 'hashchange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`hashchange_event`

5

12

3.6

8

10.6

5

≤37

18

4

11

5

1.0

See also
--------

-   [`popstate`](popstate_event)
-   [`WindowEventHandlers.onhashchange`](../windoweventhandlers/onhashchange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/hashchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/hashchange_event</a>
