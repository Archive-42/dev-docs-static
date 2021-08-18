# DedicatedWorkerGlobalScope.name

The `name` read-only property of the [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) interface returns the name that the [`Worker`](../worker) was (optionally) given when it was created. This is the name that the [`Worker()`](../worker/worker) constructor can pass to get a reference to the [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope).

## Syntax

    var nameObj = self.name;

### Value

A [`DOMString`](../domstring).

## Example

If a worker is created using a constructor with a `name` option:

    var myWorker = new Worker("worker.js", { name : "myWorker" });

the [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) will now have a name of "myWorker", returnable by running

    self.name

from inside the worker.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-dedicatedworkerglobalscope-name">HTML Living Standard<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

18

55

No

?

12.1

Yes

Yes

55

?

12.2

Yes

## See also

- [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/name</a>
