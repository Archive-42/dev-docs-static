# DedicatedWorkerGlobalScope.close()

The `close()` method of the [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) interface discards any tasks queued in the `DedicatedWorkerGlobalScope`'s event loop, effectively closing this particular scope.

## Syntax

    self.close();

## Example

If you want to close your worker instance from inside the worker itself, you can call the following:

    close();

`close()` and `self.close()` are effectively equivalent — both represent `close()` being called from inside the worker's inner scope.

**Note**: There is also a way to stop the worker from the main thread: the [`Worker.terminate`](../worker/terminate) method.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-dedicatedworkerglobalscope-close">HTML Living Standard<br />
<span class="small">The definition of 'close()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`close`

4

12

3.5

10

11.5

4

≤37

18

4

11.5

5.1

1.0

## See also

[`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/close</a>
