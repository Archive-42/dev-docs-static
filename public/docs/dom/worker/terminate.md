Worker.terminate()
==================

The `terminate()` method of the [`Worker`](../worker) interface immediately terminates the [`Worker`](../worker). This does not offer the worker an opportunity to finish its operations; it is stopped at once.

Syntax
------

    myWorker.terminate();

### Parameters

None.

### Returns

Void.

Example
-------

The following code snippet shows creation of a [`Worker`](../worker) object using the [`Worker()`](worker) constructor, which is then immediately terminated.

    var myWorker = new Worker('worker.js');

    myWorker.terminate();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-worker-terminate">HTML Living Standard<br />
<span class="small">The definition of 'Worker.terminate()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`terminate`

4

12

3.5

10

10.6

4

4

18

4

11

5.1

1.0

See also
--------

The [`Worker`](../worker) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Worker/terminate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Worker/terminate</a>
