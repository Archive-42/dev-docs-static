XMLDocument
===========

The **XMLDocument** interface represents an XML document. It inherits from the generic [`Document`](document) and does not add any specific methods or properties to it: nevertheless, several algorithms behave differently with the two types of documents.

Property
--------

*Also inherits properties from: [`Document`](document)*

 [`XMLDocument.async`](xmldocument/async) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Used with [`XMLDocument.load()`](xmldocument/load) to indicate an asynchronous request.

Methods
-------

*Also inherits methods from: [`Document`](document)*

 [`XMLDocument.load()`](xmldocument/load) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Loads an XML document.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#xmldocument">DOM<br />
<span class="small">The definition of 'XMLDocument' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#xmldocument">DOM4<br />
<span class="small">The definition of 'XMLDocument' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XMLDocument`

34

1-34

Implemented as an alias for `Document`.

≤18

1

No

21

Yes-21

Implemented as an alias for `Document`.

10

3-10

Implemented as an alias for `Document`.

37

1-37

Implemented as an alias for `Document`.

34

18-34

Implemented as an alias for `Document`.

4

21

Yes-21

Implemented as an alias for `Document`.

10

1-10

Implemented as an alias for `Document`.

2.0

1.0-2.0

Implemented as an alias for `Document`.

`async`

No

No

1-68

See [bug 1328138](https://bugzil.la/1328138) for removal.

No

No

No

No

No

4-68

See [bug 1328138](https://bugzil.la/1328138) for removal.

No

No

No

`load`

No

No

3-68

See [bug 332175](https://bugzil.la/332175) for removal.

1-3

Before version 3, Firefox supported cross-origin loads, even in cases where this would violate CORS.

No

No

No

No

No

4-68

See [bug 332175](https://bugzil.la/332175) for removal.

No

No

No

See also
--------

-   [The DOM interfaces index.](document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument</a>
