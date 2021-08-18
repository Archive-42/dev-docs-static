SVGNumberList
=============

SVG number list interface
-------------------------

The `SVGNumberList` defines a list of [`SVGNumber`](svgnumber) objects.

An `SVGNumberList` object can be designated as read only, which means that attempts to modify the object will result in an exception being thrown.

**Note:** Starting in Gecko 5.0,the `SVGNumberList` DOM interface is now indexable and can be accessed like arrays.

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td>None</td></tr><tr class="even"><td>Methods</td><td><ul><li><code>void clear()</code></li><li><a href="svgnumber"><code>SVGNumber</code></a> <code>initialize(in SVGNumber</code> newItem)</li><li><a href="svgnumber"><code>SVGNumber</code></a> <code>getItem(in unsigned long index)</code></li><li><a href="svgnumber"><code>SVGNumber</code></a> <code>insertItemBefore(in SVGNumber</code> newItem, in unsigned long index)</li><li><a href="svgnumber"><code>SVGNumber</code></a> <code>replaceItem(in SVGNumber</code> newItem, in unsigned long index)</li><li><a href="svgnumber"><code>SVGNumber</code></a> <code>removeItem(in unsigned long index)</code></li><li><a href="svgnumber"><code>SVGNumber</code></a> <code>appendItem(in SVGNumber</code> newItem)</li></ul></td></tr><tr class="odd"><td>Properties</td><td><ul><li>readonly unsigned long <code>numberOfItems</code></li><li>readonly unsigned long <code>length</code> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span></li></ul></td></tr><tr class="even"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG/types.html#InterfaceSVGNumberList">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Properties
----------

<table><thead><tr class="header"><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>numberOfItems</code></td><td>unsigned long</td><td>The number of items in the list.</td></tr><tr class="even"><td><code>length </code> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span></td><td>unsigned long</td><td>The number of items in the list.</td></tr></tbody></table>

Methods
-------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Name &amp; Arguments</th><th>Return</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>clear()</code></td><td>void</td><td><p>Clears all existing current items from the list, with the result being an empty list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="even"><td><code>initialize(in SVGNumber</code> newItem)</td><td><a href="svgnumber"><code>SVGNumber</code></a></td><td><p>Clears all existing current items from the list and re-initializes the list to hold the single item specified by <code>newItem</code>. If the inserted item is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy. The return value is the item inserted into the list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="odd"><td><code>getItem(in unsigned long index)</code></td><td><a href="svgnumber"><code>SVGNumber</code></a></td><td><p>Returns the specified item from the list. The returned item is the item itself and not a copy. Any changes made to the item are immediately reflected in the list. The first item is number <code>0</code>.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="even"><td><code>insertItemBefore(in SVGNumber</code> newItem, in unsigned long index)</td><td><a href="svgnumber"><code>SVGNumber</code></a></td><td><p>Inserts a new item into the list at the specified position. The first item is number <code>0</code>.</p><p>If <code>newItem</code> is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy. If the item is already in this list, note that the index of the item to insert before is before the removal of the item.</p><p>If the <code>index</code> is equal to <code>0</code>, then the new item is inserted at the front of the list. If the index is greater than or equal to <code>numberOfItems</code>, then the new item is appended to the end of the list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="odd"><td><code>replaceItem(in SVGNumber</code> newItem, in unsigned long index)</td><td><a href="svgnumber"><code>SVGNumber</code></a></td><td><p>Replaces an existing item in the list with a new item. If <code>newItem</code> is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy. If the item is already in this list, note that the index of the item to replace is before the removal of the item.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li><li>a <a href="domexception"><code>DOMException</code></a> with code <code>INDEX_SIZE_ERR</code> is raised if <code>index</code> is greater than or equal to <code>numberOfItems</code>.</li></ul></td></tr><tr class="even"><td><code>removeItem(in unsigned long index)</code></td><td><a href="svgnumber"><code>SVGNumber</code></a></td><td><p>Removes an existing item from the list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li><li>a <a href="domexception"><code>DOMException</code></a> with code <code>INDEX_SIZE_ERR</code> is raised if <code>index</code> is greater than or equal to <code>numberOfItems</code>.</li></ul></td></tr><tr class="odd"><td><code>appendItem(in SVGNumber</code> newItem)</td><td><a href="svgnumber"><code>SVGNumber</code></a></td><td><p>Inserts a new item at the end of the list. If <code>newItem</code> is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr></tbody></table>

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

`SVGNumberList`

5

12

1.5

9

15

5

≤37

18

4

14

4

1.0

`appendItem`

6

12

3

10

15

6

≤37

18

4

14

6

1.0

`clear`

6

12

3

10

15

6

≤37

18

4

14

6

1.0

`getItem`

6

12

3

10

15

6

≤37

18

4

14

6

1.0

`initialize`

6

12

3

10

15

6

≤37

18

4

14

6

1.0

`insertItemBefore`

6

12

3

10

15

6

≤37

18

4

14

6

1.0

`length`

35

79

5

No

15

13.1

37

35

5

14

13.4

3.0

`numberOfItems`

6

12

3

10

15

6

≤37

18

4

14

6

1.0

`removeItem`

6

12

3

10

15

6

≤37

18

4

14

6

1.0

`replaceItem`

6

12

3

10

15

6

≤37

18

4

14

6

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGNumberList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGNumberList</a>
