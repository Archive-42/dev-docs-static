# DocumentType

The `DocumentType` interface represents a [`Node`](node) containing a doctype.

## Properties

_Inherits properties from its parent, [`Node`](node), and implements the [`ChildNode`](childnode) interface._

<span class="page-not-created">`DocumentType.entities`</span> <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`NamedNodeMap`](namednodemap) of entities declared in the DTD. Every node in this map implements the <span class="page-not-created">`Entity`</span> interface.

<span class="page-not-created">`DocumentType.internalSubset`</span> <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) of the internal subset, or `null` if there is none. Eg `"<!ELEMENT foo (bar)>"`.

<span class="page-not-created">`DocumentType.name`</span> <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring), eg `"html"` for `<!DOCTYPE HTML>`.

<span class="page-not-created">`DocumentType.notations`</span> <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`NamedNodeMap`](namednodemap) with notations declared in the DTD. Every node in this map implements the [`Notation`](notation) interface.

<span class="page-not-created">`DocumentType.publicId`</span> <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring), eg `"-//W3C//DTD HTML 4.01//EN"`, empty string for HTML5.

<span class="page-not-created">`DocumentType.systemId`</span> <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring), eg `"http://www.w3.org/TR/html4/strict.dtd"`, empty string for HTML5.

## Methods

_Inherits methods from its parent, [`Node`](node), and implements the [`ChildNode`](childnode) interface._

[`ChildNode.remove()`](childnode/remove) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Removes the object from its parent children list.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#documenttype">DOM<br />
<span class="small">The definition of 'DocumentType' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added implementation of the <a href="childnode"><code>ChildNode</code></a> interface.<br />
Removed the <code>internalSubset</code>, <code>entities</code>, and <code>notation</code> properties.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-412266927">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'DocumentType' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-412266927">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'DocumentType' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the <code>publicID</code>, <code>systemID</code>, and <code>internalSubset</code> properties.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-412266927">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'DocumentType' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`DocumentType`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`entities`

1-34

12-79

1-6

9

≤12.1-21

3-10

1-37

18-34

4-6

≤12.1-21

1-10

1.0-2.0

`internalSubset`

1-37

12-79

No

9

≤12.1-24

3-10.1

1-37

18-37

No

≤12.1-24

1-10.3

1.0-3.0

`name`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`notations`

1-34

12-79

1-6

9

≤12.1-21

3-10

1-37

18-34

4-6

≤12.1-21

1-10

1.0-2.0

`publicId`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`systemId`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

## See also

- [The DOM interfaces index.](document_object_model)
- <span class="page-not-created">`Entity`</span>
- [`Notation`](notation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DocumentType</a>
