Text
====

The `Text` interface represents the textual content of [`Element`](element) or [`Attr`](attr).

If an element has no markup within its content, it has a single child implementing `Text` that contains the element's text. However, if the element contains markup, it is parsed into information items and `Text` nodes that form its children.

New documents have a single `Text` node for each block of text. Over time, more `Text` nodes may be created as the document's content changes. The [`Node.normalize()`](node/normalize) method merges adjacent `Text` objects back into a single node for each block of text.

Constructor
-----------

 [`Text()`](text/text) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a `Text` node with the parameter as its textual content.

Properties
----------

*Inherits properties from its parent, [`CharacterData`](characterdata).*

 [`Text.assignedSlot`](text/assignedslot) <span class="badge inline readonly">Read only </span>   
Returns a [`HTMLSlotElement`](htmlslotelement) representing the [`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot) the node is inserted in.

 [`Text.isElementContentWhitespace`](text/iselementcontentwhitespace) <span class="badge inline readonly">Read only </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating whether or not the text node contains only whitespace.

 [`Text.wholeText`](text/wholetext) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) containing the text of all `Text` nodes logically adjacent to this [`Node`](node), concatenated in document order.

Methods
-------

*Inherits methods from its parent, [`CharacterData`](characterdata).*

 [`Text.replaceWholeText`](text/replacewholetext) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Replaces the text of the current node and all logically adjacent nodes with the specified text.

<span class="internal">[`Text.splitText`](text/splittext)</span>  
Breaks the node into two nodes at a specified offset.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#text">DOM<br />
<span class="small">The definition of 'Text' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Removed the <code>isElementContentWhitespace</code> property.<br />
Removed the <code>replaceWholeText()</code> method.<br />
Added the <code>Text()</code> constructor.<br />
Added the <code>assignedSlot</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-1312295772">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Text' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the <code>isElementContentWhitespace</code> and <code>wholeText</code> properties.<br />
Added the <code>replaceWholeText()</code> method.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-1312295772">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Text' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-1312295772">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Text' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Text`

1

12

Yes

5

Yes

1

Yes

18

Yes

Yes

1

?

`Text`

28

16

24

No

15

8

Yes

28

24

14

8

2.0

`assignedSlot`

53

≤18

Yes

No

40

10.1

53

53

Yes

41

10.3

6.0

`isElementContentWhitespace`

No

No

Yes-10

No

No

No

No

No

Yes-10

No

No

No

`replaceWholeText`

Yes-45

12-79

Yes-10

9

Yes-32

4-10.1

Yes-45

Yes-45

Yes-10

Yes-32

3-10.3

Yes-5.0

`splitText`

1

Before Chrome 30, the `offset` argument was optional.

12

1

5

Yes

Before Opera 17, the `offset` argument was optional.

1

The `offset` argument is optional.

Yes

Before version 4.4, the `offset` argument was optional.

18

Before Chrome 30, the `offset` argument was optional.

4

Yes

Before Opera 17, the `offset` argument was optional.

1

The `offset` argument is optional.

1.0

Before Samsung Internet 2.0, the `offset` argument was optional.

`wholeText`

1

12

3.5

9

Yes

4

Yes

18

4

Yes

3.2

?

See also
--------

-   [The DOM interfaces index](document_object_model).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Text" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Text</a>
