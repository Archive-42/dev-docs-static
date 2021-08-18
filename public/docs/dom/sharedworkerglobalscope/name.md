SharedWorkerGlobalScope.name
============================

The `name` read-only property of the [`SharedWorkerGlobalScope`](../sharedworkerglobalscope) interface returns the name that the [`SharedWorker`](../sharedworker) was (optionally) given when it was created. This is the name that the [`SharedWorker()`](../sharedworker/sharedworker) constructor can pass to get a reference to the [`SharedWorkerGlobalScope`](../sharedworkerglobalscope).

Syntax
------

    var nameObj = self.name;

### Value

A [`DOMString`](../domstring).

Example
-------

If a shared worker is created using a constructor with a `name` option:

    var myWorker = new SharedWorker("worker.js", { name : "mySharedWorker" });

the [`SharedWorkerGlobalScope`](../sharedworkerglobalscope) will now have a name of "mySharedWorker", returnable by running

    self.name

from inside the shared worker.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-sharedworkerglobalscope-name">HTML Living Standard<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`name`

Yes

79

55

No

10.6

No

Yes

40

55

Yes

No

4.0

See also
--------

-   [`SharedWorkerGlobalScope`](../sharedworkerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/name</a>
