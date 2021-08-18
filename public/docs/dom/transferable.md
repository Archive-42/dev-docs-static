Transferable
============

The `Transferable` interface represents an object that can be transfered between different execution contexts, like the main thread and Web workers.

This is an abstract interface and there is no object of this type. This interface does not define any method or property; it is merely a tag indicating objects that can be used in specific conditions, such as being transfered to a [`Worker`](worker) using the [`Worker.postMessage()`](worker/postmessage) method.

**Note:** The `Transferable` interface technically no longer exists. The *functionality* of `Transferable` objects still exists, however, but is implemented at a more fundamental level (technically speaking, using the `[Transferable]` [WebIDL](https://developer.mozilla.org/en-US/docs/Glossary/WebIDL) extended attribute).

The [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), [`MessagePort`](messageport), [`ImageBitmap`](imagebitmap) and [`OffscreenCanvas`](offscreencanvas) types implement this interface.

Properties
----------

*The `Transferable` interface does not implement or inherit specific properties.*

Methods
-------

*The `Transferable` interface does not implement or inherit specific properties.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/infrastructure.html#transferable-objects">HTML Living Standard<br />
<span class="small">The definition of 'Transferable' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Replaced <code>Transferable</code> interface with <code>[Transferable]</code> Web IDL extended attribute.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/infrastructure.html#transferable-objects">HTML5<br />
<span class="small">The definition of 'Transferable' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Transferable`

Yes

12

4

10

Internet Explorer 10 only accepts a single `Transferable` object as parameter, but not an array.

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

See also
--------

-   Interfaces implementing it: [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), [`MessagePort`](messageport), [`ImageBitmap`](imagebitmap).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Transferable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Transferable</a>
