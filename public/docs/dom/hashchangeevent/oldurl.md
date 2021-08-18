HashChangeEvent.oldURL
======================

The `oldURL` read-only property of the [`HashChangeEvent`](../hashchangeevent) interface returns the previous URL from which the window was navigated.

Syntax
------

    let oldEventUrl = event.oldURL;

### Value

A [`DOMString`](../domstring).

Example
-------

    window.addEventListener('hashchange', function(event) {
      console.log('Hash changed from ' + event.oldURL);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hashchangeevent-oldurl">HTML Living Standard<br />
<span class="small">The definition of 'HashChangeEvent: oldURL' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`oldURL`

Yes

12

6

No

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent/oldURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent/oldURL</a>
