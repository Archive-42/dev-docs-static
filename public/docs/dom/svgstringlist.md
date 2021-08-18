SVGStringList
=============

SVG string list interface
-------------------------

The `SVGStringList` defines a list of [`DOMString`](domstring) objects.

An `SVGStringList` object can be designated as read only, which means that attempts to modify the object will result in an exception being thrown.

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td><em>None</em></td></tr><tr class="even"><td>Methods</td><td><ul><li><code>void clear()</code></li><li><a href="domstring"><code>DOMString</code></a> <code>initialize(in DOMString</code> <em>newItem</em>)</li><li><a href="domstring"><code>DOMString</code></a> <code>getItem(in unsigned long index)</code></li><li><a href="domstring"><code>DOMString</code></a> <code>insertItemBefore(in DOMString</code> <em>newItem</em>, in unsigned long <em>index</em>)</li><li><a href="domstring"><code>DOMString</code></a> <code>replaceItem(in DOMString</code> <em>newItem</em>, in unsigned long <em>index</em>)</li><li><a href="domstring"><code>DOMString</code></a> <code>removeItem(in unsigned long index)</code></li><li><a href="domstring"><code>DOMString</code></a> <code>appendItem(in DOMString</code> <em>newItem</em>)</li></ul></td></tr><tr class="odd"><td>Properties</td><td><ul><li>readonly unsigned long <code>numberOfItems</code></li><li>readonly unsigned long <code>length</code> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span></li></ul></td></tr><tr class="even"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGStringList">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Properties
----------

<table><thead><tr class="header"><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>numberOfItems</code></td><td><code>unsigned long</code></td><td>The number of items in the list.</td></tr><tr class="even"><td><code>length</code></td><td><code>unsigned long</code></td><td>A mirror of the value in <code>numberOfItems</code>, for consistency with other interfaces. <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span></td></tr></tbody></table>

Methods
-------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Name &amp; Arguments</th><th>Return</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>clear()</code></td><td><em>void</em></td><td><p>Clears all existing current items from the list, with the result being an empty list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="even"><td><code>initialize(in DOMString</code> <em>newItem</em>)</td><td><a href="domstring"><code>DOMString</code></a></td><td><p>Clears all existing current items from the list and re-initializes the list to hold the single item specified by the parameter. If the inserted item is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy. The return value is the item inserted into the list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="odd"><td><code>getItem(in unsigned long index)</code></td><td><a href="domstring"><code>DOMString</code></a></td><td><p>Returns the specified item from the list. The returned item is the item itself and not a copy. Any changes made to the item are immediately reflected in the list. The first item is number 0.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="even"><td><code>insertItemBefore(in DOMString</code> <em>newItem</em>, in unsigned long <em>index</em>)</td><td><a href="domstring"><code>DOMString</code></a></td><td><p>Inserts a new item into the list at the specified position. The first item is number 0. If <code>newItem</code> is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy. If the item is already in this list, note that the index of the item to insert before is before the removal of the item. If the <code>index</code> is equal to 0, then the new item is inserted at the front of the list. If the index is greater than or equal to <code>numberOfItems</code>, then the new item is appended to the end of the list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="odd"><td><code>replaceItem(in DOMString</code> <em>newItem</em>, in unsigned long <em>index</em>)</td><td><a href="domstring"><code>DOMString</code></a></td><td><p>Replaces an existing item in the list with a new item. If <code>newItem</code> is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy. If the item is already in this list, note that the index of the item to replace is before the removal of the item.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li><li>a <a href="domexception"><code>DOMException</code></a> with code <code>INDEX_SIZE_ERR</code> is raised if the index number is greater than or equal to <code>numberOfItems</code>.</li></ul></td></tr><tr class="even"><td><code>removeItem(in unsigned long index)</code></td><td><a href="domstring"><code>DOMString</code></a></td><td><p>Removes an existing item from the list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li><li>a <a href="domexception"><code>DOMException</code></a> with code <code>INDEX_SIZE_ERR</code> is raised if the index number is greater than or equal to <code>numberOfItems</code>.</li></ul></td></tr><tr class="odd"><td><code>appendItem(in DOMString</code> <em>newItem</em>)</td><td><a href="domstring"><code>DOMString</code></a></td><td><p>Inserts a new item at the end of the list. If <code>newItem</code> is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr></tbody></table>

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

`SVGStringList`

5

12

12

Since version 13, `SVGStringList` is indexable like Array which is a non-standard behavior.

9

15

5

≤37

18

14

`SVGStringList` is indexable like Array which is a non-standard behavior.

14

4

1.0

`appendItem`

5

12

12

9

15

5

≤37

18

14

14

4

1.0

`clear`

5

12

12

9

15

5

≤37

18

14

14

4

1.0

`getItem`

5

12

12

9

15

5

≤37

18

14

14

4

1.0

`initialize`

5

12

12

9

15

5

≤37

18

14

14

4

1.0

`insertItemBefore`

5

12

12

9

15

5

≤37

18

14

14

4

1.0

`length`

Yes

≤79

13

No

Yes

Yes

Yes

Yes

14

Yes

Yes

Yes

`numberOfItems`

5

12

12

9

15

5

1

18

14

14

4

1.0

`removeItem`

5

12

12

9

15

5

≤37

18

14

14

4

1.0

`replaceItem`

5

12

12

9

15

5

≤37

18

14

14

4

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGStringList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGStringList</a>
