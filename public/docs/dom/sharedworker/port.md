SharedWorker.port
=================

The `port` property of the [`SharedWorker`](../sharedworker) interface returns a [`MessagePort`](../messageport) object used to communicate and control the shared worker.

Syntax
------

    myWorker.port;

### Value

A [`MessagePort`](../messageport) object.

Example
-------

The following code snippet shows creation of a `SharedWorker` object using the [`SharedWorker()`](sharedworker) constructor. Multiple scripts can then access the worker through a [`MessagePort`](../messageport) object accessed using the `SharedWorker.port` property — the port is started using its `start()` method:

    var myWorker = new SharedWorker('worker.js');
    myWorker.port.start();

For a full example, see our [Basic shared worker example](https://github.com/mdn/simple-shared-worker) ([run shared worker](https://mdn.github.io/simple-shared-worker/).)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-sharedworker-port">HTML Living Standard<br />
<span class="small">The definition of 'AbstractWorker.onerror' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`port`

4

79

29

No

10.6

5-6.1

No

No

33

11-14

5.1-7

4.0-5.0

See also
--------

-   The [`SharedWorker`](../sharedworker) interface it belongs to.
-   [another multiply demo](https://anlexn.github.io/shared-worker-mdn/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/port" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/port</a>
