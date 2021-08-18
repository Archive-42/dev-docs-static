WorkerGlobalScope.onlanguagechange
==================================

The `onlanguagechange` property of the [`WorkerGlobalScope`](../workerglobalscope) interface represents an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) to be called when the `languagechange` event occurs and bubbles through the [`Worker`](../worker).

Syntax
------

    self.onlanguagechange = function() { ... };

Example
-------

The following code snippet shows an `onlanguagechange` handler set inside a worker:

    self.onlanguagechange = function() {
      console.log('Your preferred language settings have been changed');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-workerglobalscope-onlanguagechange">HTML Living Standard<br />
<span class="small">The definition of 'WorkerGlobalScope.onlanguagechange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onlanguagechange`

4

12

74

Yes

11.5

4

37

40

No

Yes

5.1

4.0

See also
--------

The [`WorkerGlobalScope`](../workerglobalscope) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onlanguagechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onlanguagechange</a>
