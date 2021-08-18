WorkerGlobalScope.ononline
==========================

The `ononline` property of the [`WorkerGlobalScope`](../workerglobalscope) interface represents an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) to be called when the `online` event occurs and bubbles through the [`Worker`](../worker).

Syntax
------

    self.ononline = function() { ... };

Example
-------

The following code snippet shows an `ononline` handler set inside a worker:

    self.ononline = function() {
      console.log('Your worker is now online');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-workerglobalscope-ononline">HTML Living Standard<br />
<span class="small">The definition of 'WorkerGlobalScope.ononline' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`ononline`

4

≤79

29

No

?

Yes

40

40

29

?

Yes

4.0

See also
--------

The [`WorkerGlobalScope`](../workerglobalscope) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/ononline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/ononline</a>
