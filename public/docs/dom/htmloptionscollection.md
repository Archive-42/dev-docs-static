HTMLOptionsCollection
=====================

The `HTMLOptionsCollection` interface represents a collection of `<option>` HTML elements (in document order) and offers methods and properties for selecting from the list as well as optionally altering its items. This object is returned only by the `options` property of [select](htmlselectelement).

Properties
----------

<table><thead><tr class="header"><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>length</code></td><td><a href="https://developer.mozilla.org/en-US/docs/unsigned_long"><code>unsigned long</code></a></td><td>As optionally allowed by the spec, this property isn't read-only. You can either remove options from the end by lowering the value, or add blank options at the end by raising the value. Mozilla allows this, while other implementations could potentially throw a <a href="domexception">DOMException</a>.</td></tr></tbody></table>

Methods
-------

*This interface inherits the methods of its parent, [`HTMLCollection`](htmlcollection).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#the-htmloptionscollection-interface">HTML Living Standard<br />
<span class="small">The definition of 'HTMLOptionsCollection' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`HTMLOptionsCollection`

1

12

1

Yes

Yes

3

1

18

4

Yes

1

1.0

`add`

1

≤18

4

No

Yes

3

1

18

4

Yes

1

1.0

`length`

1

13

1

Yes

Yes

3

1

18

4

Yes

1

1.0

`remove`

1

≤18

4

No

Yes

3.1

1

18

4

Yes

1

1.0

`selectedIndex`

1

≤18

1

No

Yes

3

1

18

4

Yes

1

1.0

See also
--------

-   [HTMLCollection](htmlcollection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionsCollection</a>
