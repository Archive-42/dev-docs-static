Range
=====

The `Range` interface represents a fragment of a document that can contain nodes and parts of text nodes.

A range can be created by using the [`Document.createRange()`](document/createrange) method. Range objects can also be retrieved by using the [`getRangeAt()`](selection/getrangeat) method of the [`Selection`](selection) object or the [`caretRangeFromPoint()`](document/caretrangefrompoint) method of the [`Document`](document) object.

There also is the [`Range()`](range/range) constructor available.

Properties
----------

*There are no inherited properties.*

 [`Range.collapsed`](range/collapsed) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the range's start and end points are at the same position.

 [`Range.commonAncestorContainer`](range/commonancestorcontainer) <span class="badge inline readonly">Read only </span>   
Returns the deepest [`Node`](node) that contains the `startContainer` and `endContainer` nodes.

 [`Range.endContainer`](range/endcontainer) <span class="badge inline readonly">Read only </span>   
Returns the [`Node`](node) within which the `Range` ends.

 [`Range.endOffset`](range/endoffset) <span class="badge inline readonly">Read only </span>   
Returns a number representing where in the `endContainer` the `Range` ends.

 [`Range.startContainer`](range/startcontainer) <span class="badge inline readonly">Read only </span>   
Returns the [`Node`](node) within which the `Range` starts.

 [`Range.startOffset`](range/startoffset) <span class="badge inline readonly">Read only </span>   
Returns a number representing where in the `startContainer` the `Range` starts.

Constructor
-----------

 [`Range()`](range/range) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a `Range` object with the global [`Document`](document) as its start and end.

Methods
-------

*There are no inherited methods.*

[`Range.setStart()`](range/setstart)  
Sets the start position of a `Range`.

[`Range.setEnd()`](range/setend)  
Sets the end position of a `Range`.

[`Range.setStartBefore()`](range/setstartbefore)  
Sets the start position of a `Range` relative to another [`Node`](node).

[`Range.setStartAfter()`](range/setstartafter)  
Sets the start position of a `Range` relative to another [`Node`](node).

[`Range.setEndBefore()`](range/setendbefore)  
Sets the end position of a `Range` relative to another [`Node`](node).

[`Range.setEndAfter()`](range/setendafter)  
Sets the end position of a `Range` relative to another [`Node`](node).

[`Range.selectNode()`](range/selectnode)  
Sets the `Range` to contain the [`Node`](node) and its contents.

[`Range.selectNodeContents()`](range/selectnodecontents)  
Sets the `Range` to contain the contents of a [`Node`](node).

[`Range.collapse()`](range/collapse)  
Collapses the `Range` to one of its boundary points.

[`Range.cloneContents()`](range/clonecontents)  
Returns a [`DocumentFragment`](documentfragment) copying the nodes of a `Range`.

[`Range.deleteContents()`](range/deletecontents)  
Removes the contents of a `Range` from the [`Document`](document).

[`Range.extractContents()`](range/extractcontents)  
Moves contents of a `Range` from the document tree into a [`DocumentFragment`](documentfragment).

[`Range.insertNode()`](range/insertnode)  
Insert a [`Node`](node) at the start of a `Range`.

[`Range.surroundContents()`](range/surroundcontents)  
Moves content of a `Range` into a new [`Node`](node).

[`Range.compareBoundaryPoints()`](range/compareboundarypoints)  
Compares the boundary points of the `Range` with another `Range`.

[`Range.cloneRange()`](range/clonerange)  
Returns a `Range` object with boundary points identical to the cloned `Range`.

[`Range.detach()`](range/detach)  
Releases the `Range` from use to improve performance.

[`Range.toString()`](range/tostring)  
Returns the text of the `Range`.

 [`Range.compareNode()`](range/comparenode) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns a constant representing whether the [`Node`](node) is before, after, inside, or surrounding the range.

 [`Range.comparePoint()`](range/comparepoint) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns -1, 0, or 1 indicating whether the point occurs before, inside, or after the `Range`.

 [`Range.createContextualFragment()`](range/createcontextualfragment)<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a [`DocumentFragment`](documentfragment) created from a given string of code.

 [`Range.getBoundingClientRect()`](range/getboundingclientrect) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a [`DOMRect`](domrect) object which bounds the entire contents of the `Range`; this would be the union of all the rectangles returned by [`range.getClientRects()`](range/getclientrects).

 [`Range.getClientRects()`](range/getclientrects) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a list of [`DOMRect`](domrect) objects that aggregates the results of [`Element.getClientRects()`](element/getclientrects) for all the elements in the `Range`.

 [`Range.intersectsNode()`](range/intersectsnode) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a `boolean` indicating whether the given node intersects the `Range`.

 [`Range.isPointInRange()`](range/ispointinrange) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a `boolean` indicating whether the given point is in the `Range`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-range">DOM<br />
<span class="small">The definition of 'Range' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Do not use <code>RangeException</code> anymore, use <code>DOMException</code> instead.<br />
Made the second parameter of <code>collapse()</code> optional.<br />
Added the methods <code>isPointInRange()</code>, <code>comparePoint()</code>, and <code>intersectsNode()</code>.<br />
Added the constructor <code>Range()</code>.</td></tr><tr class="even"><td><a href="https://w3c.github.io/DOM-Parsing/#extensions-to-the-range-interface">DOM Parsing and Serialization<br />
<span class="small">The definition of 'Extensions to Range' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the method <code>createContextualFragment()</code>.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-range-interface">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Extensions to Range' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the methods <code>getClientRects()</code> and <code>getBoundingClientRect()</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level-2-Range-Interface">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`Range`

1

12

1

Starting with Firefox 13, the `Range` object throws a `DOMException` as defined in DOM 4, instead of a `RangeException` defined in prior specifications.

9

9

1

1

18

4

Starting with Firefox 13, the `Range` object throws a `DOMException` as defined in DOM 4, instead of a `RangeException` defined in prior specifications.

10.1

1

1.0

`Range`

29

15

24

No

16

6.1

≤37

29

24

16

8

2.0

`cloneContents`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`cloneRange`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`collapse`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`collapsed`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`commonAncestorContainer`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`compareBoundaryPoints`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`compareNode`

1-45

No

1-3

No

15-32

3

1-45

18-45

No

14-32

1

1.0-5.0

`comparePoint`

1

17

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`createContextualFragment`

1

12

1

11

≤12.1

9

1

18

4

≤12.1

Yes

1.0

`deleteContents`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`detach`

1

Starting in Chrome 37, this method is a no-op and has no effect.

12

1-15

Starting in Firefox 15.0, this method is a no-op and has no effect.

9

9

Starting in Opera 24, this method is a no-op and has no effect.

1

Since August 2015 this method is a no-op in [WebKit-based browsers](https://webkit.org/b/148454).

1

Starting in WebView 37, this method is a no-op and has no effect.

18

Starting in Chrome 37, this method is a no-op and has no effect.

4-15

Starting in Firefox 15.0, this method is a no-op and has no effect.

10.1

Starting in Opera 24, this method is a no-op and has no effect.

1

Since August 2015 this method is a no-op in [WebKit-based browsers](https://webkit.org/b/148454).

1.0

Starting in Samsung Internet 3.0, this method is a no-op and has no effect.

`endContainer`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`endOffset`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`extractContents`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`getBoundingClientRect`

4

12

4

9

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`getClientRects`

4

12

4

9

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`insertNode`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`intersectsNode`

1

17

17

No

≤12.1

3

1

18

19

≤12.1

1

1.0

`isPointInRange`

1

15

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`selectNode`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`selectNodeContents`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`setEnd`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`setEndAfter`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`setEndBefore`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`setStart`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`setStartAfter`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`setStartBefore`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`startContainer`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`startOffset`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`surroundContents`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`toString`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

See also
--------

-   [The DOM interfaces index](document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range</a>
