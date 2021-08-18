WorkerGlobalScope.performance
=============================

The `performance` read-only property of the [`WorkerGlobalScope`](../workerglobalscope) interface returns a [`Performance`](../performance) object to be used on the worker.

Not all [`Performance`](../performance) properties and methods are available to Web workers.

This property is <span class="badge inline readonly">Read only </span>.

Syntax
------

    var perfObj = self.performance;

### Return Value

A [`Performance`](../performance) object.

Example
-------

If you called

    console.log(performance);

inside a worker (which would basically be the equivalent of `self.console.log(self.performance);`, as these are being called on the worker scope, which can be referenced with [`WorkerGlobalScope.self`](self)), you will get a <span class="page-not-created">`WorkerPerformance`</span> object written to the console — something like the following:

    WorkerPerformance {now: function}
      __proto__: WorkerPerformance
        constructor: function WorkerPerformance() { [native code] }
        now: function now() { [native code] }
        __proto__: Object

You could use this performance object to return performance data, as you might do with a normal [`Performance`](../performance) object.

**Note**: Firefox has a bug with using `console.log` inside shared/service workers (see [bug 1058644](https://bugzilla.mozilla.org/show_bug.cgi?id=1058644)), which may return strange results, but this should be fixed soon.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/hr-time-2/#the-performance-attribute">High Resolution Time Level 2<br />
<span class="small">The definition of 'performance' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines WorkerGlobalScope.performance.</td></tr></tbody></table>

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

`performance`

Yes

≤79

34

No

?

Yes

Yes

Yes

34

?

Yes

Yes

See also
--------

-   [`Performance`](../performance)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/performance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/performance</a>
