WorkerGlobalScope.console
=========================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `console` read-only property of the [`WorkerGlobalScope`](../workerglobalscope) interface returns a [`Console`](../console) object providing access to the browser console for the worker.

Syntax
------

    var consoleObj = self.console;

### Value

A [`Console`](../console) object.

Example
-------

This property allows you to have access to a browser console for debugging purposes, inside a worker. So for example you could call

    console.log('test');

inside a worker (which would basically be the equivalent of `self.console.log('test');`, as these are being called on the worker scope, which can be referenced with [`WorkerGlobalScope.self`](self)), to return a test message out to the browser console.

If you are calling `console.log()` from a [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) or other worker scope that acts on a single loaded window, that tab's web console will receive the logs. However, If you are calling `console.log()` from a [`SharedWorkerGlobalScope`](../sharedworkerglobalscope), the global browser console will receive the logs.

Specifications
--------------

Not yet part of any specification.

Browser compatibility
---------------------

No compatibility data found for `api.WorkerGlobalScope.console`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`Console`](../console)
-   [`WorkerGlobalScope`](../workerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/console" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/console</a>
