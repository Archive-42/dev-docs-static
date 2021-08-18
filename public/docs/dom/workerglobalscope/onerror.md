WorkerGlobalScope.onerror
=========================

The `onerror` property of the [`WorkerGlobalScope`](../workerglobalscope) interface represents an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) to be called when the `error` event occurs and bubbles through the [`Worker`](../worker).

Syntax
------

    self.onerror = function() { ... };

Example
-------

The following code snippet shows an `onerror` handler set inside a worker:

    self.onerror = function() {
      console.log('There is an error inside your worker!');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-workerglobalscope-onerror">HTML Living Standard<br />
<span class="small">The definition of 'WorkerGlobalScope.onerror' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onerror`

4

12

3.5

Yes

11.5

4

37

40

4

Yes

5.1

4.0

See also
--------

The [`WorkerGlobalScope`](../workerglobalscope) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onerror</a>
