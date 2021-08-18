SharedWorkerGlobalScope.close()
===============================

The `close()` method of the [`SharedWorkerGlobalScope`](../sharedworkerglobalscope) interface discards any tasks queued in the `SharedWorkerGlobalScope`'s event loop, effectively closing this particular scope.

Syntax
------

    self.close();

Example
-------

If you want to close your worker instance from inside the worker itself, you can call the following:

    close();

`close()` and `self.close()` are effectively equivalent — both represent `close()` being called from inside the worker's inner scope.

**Note**: There is also a way to stop the worker from the main thread: the [`Worker.terminate`](../worker/terminate) method.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-sharedworkerglobalscope-close">HTML Living Standard<br />
<span class="small">The definition of 'close()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`close`

4

79

29

No

11.5

5

≤37

18

29

11

7

1.0

**General note:** In newer browser versions, `close()` is available on `SharedWorkerGlobalScope` and [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope/close). In older browser versions, it is available on [`WorkerGlobalScope`](../workerglobalscope/close). This change was made to stop `close()` being available on service workers, as it isn't supposed to be used there and always throws an exception when called (see [bug 1336043](https://bugzilla.mozilla.org/show_bug.cgi?id=1336043)).

See also
--------

[`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/close</a>
