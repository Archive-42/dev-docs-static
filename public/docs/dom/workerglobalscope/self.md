WorkerGlobalScope.self
======================

The `self` read-only property of the [`WorkerGlobalScope`](../workerglobalscope) interface returns a reference to the `WorkerGlobalScope` itself. Most of the time it is a specific scope like [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope), [`SharedWorkerGlobalScope`](../sharedworkerglobalscope), or [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope).

Syntax
------

    var selfRef = self;

### Value

A global scope object (differs depending on the type of worker you are dealing with, as indicated above).

Example
-------

If you called

    console.log(self);

inside a worker, you will get a worker global scope of the same type as that worker object written to the console — something like the following:

    DedicatedWorkerGlobalScope {
    undefined: undefined, Infinity: Infinity, Math: MathConstructor, NaN: NaN, Intl: Object…}
        Infinity: Infinity
        Array: function Array() { [native code] }
          arguments: null
          caller: null
          isArray: function isArray() { [native code] }
          length: 1
          name: "Array"
          observe: function observe() { [native code] }
          prototype: Array[0]
          unobserve: function unobserve() { [native code] }
          __proto__: function Empty() {}
          <function scope>
        ArrayBuffer: function ArrayBuffer() { [native code] }
        Blob: function Blob() { [native code] }
        Boolean: function Boolean() { [native code] }
        DataView: function DataView() { [native code] }
        Date: function Date() { [native code] }
        DedicatedWorkerGlobalScope: function DedicatedWorkerGlobalScope() { [native code] }
        Error: function Error() { [native code] }
    // etc. etc.

This provides a full list of the objects available to that worker scope, so it is quite a useful test if you want to see whether something is available to your worker or not. We also maintain a list of [Functions and classes available to Web Workers](../web_workers_api/functions_and_classes_available_to_workers).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-workerglobalscope-self">HTML Living Standard<br />
<span class="small">The definition of 'self' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`self`

4

12

3.5

Yes

11.5

4

37

40

34

Yes

5.1

4.0

See also
--------

[`WorkerGlobalScope`](../workerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/self" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/self</a>
