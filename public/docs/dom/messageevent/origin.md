MessageEvent.origin
===================

The `origin` read-only property of the [`MessageEvent`](../messageevent) interface is a [`USVString`](../usvstring) representing the origin of the message emitter.

Syntax
------

    var origin = messageEvent.origin;

### Value

A [`USVString`](../usvstring) representing the origin.

Example
-------

    myWorker.onmessage = function(e) {
      result.textContent = e.data;
      console.log('Message received from worker');
      console.log(e.origin);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-messageevent-origin">HTML Living Standard<br />
<span class="small">The definition of 'MessageEvent: origin' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`origin`

1

12

4

9

Yes

4

1

Yes

4

Yes

3

Yes

`USVString_type`

Yes

≤79

55

No

?

?

Yes

Yes

55

?

?

Yes

See also
--------

-   [`ExtendableMessageEvent`](../extendablemessageevent) — similar to this interface but used in interfaces that needs to give more flexibility to authors.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/origin</a>
