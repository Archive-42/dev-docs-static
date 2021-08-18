# DocumentFragment

The `DocumentFragment` interface represents a minimal document object that has no parent. It is used as a lightweight version of [`Document`](document) that stores a segment of a document structure comprised of nodes just like a standard document. The key difference is due to the fact that the document fragment isn't part of the active document tree structure. Changes made to the fragment don't affect the document (even on [reflow](https://developer.mozilla.org/en-US/docs/Glossary/Reflow)) or incur any performance impact when changes are made.

## Constructor

[`DocumentFragment()`](documentfragment/documentfragment)  
Creates and returns a new `DocumentFragment` object.

## Properties

_This interface has no specific properties, but inherits those of its parent, [`Node`](node), and implements those of the [`ParentNode`](parentnode) interface._

[`DocumentFragment.childElementCount`](documentfragment/childelementcount) <span class="badge inline readonly">Read only </span>  
Returns the amount of child [`elements`](element) the `DocumentFragment` has.

[`DocumentFragment.children`](documentfragment/children) <span class="badge inline readonly">Read only </span>  
Returns a live [`HTMLCollection`](htmlcollection) containing all objects of type [`Element`](element) that are children of the `DocumentFragment` object.

[`DocumentFragment.firstElementChild`](documentfragment/firstelementchild) <span class="badge inline readonly">Read only </span>  
Returns the [`Element`](element) that is the first child of the `DocumentFragment` object, or `null` if there is none.

[`DocumentFragment.lastElementChild`](documentfragment/lastelementchild) <span class="badge inline readonly">Read only </span>  
Returns the [`Element`](element) that is the last child of the `DocumentFragment` object, or `null` if there is none.

## Methods

_This interface inherits the methods of its parent, [`Node`](node), and implements those of the [`ParentNode`](parentnode) interface._

[`DocumentFragment.append()`](documentfragment/append)  
Inserts a set of [`Node`](node) objects or [`DOMString`](domstring) objects after the last child of the document fragment.

[`DocumentFragment.prepend()`](documentfragment/prepend)  
Inserts a set of [`Node`](node) objects or [`DOMString`](domstring) objects before the first child of the document fragment.

[`DocumentFragment.querySelector()`](documentfragment/queryselector)  
Returns the first [`Element`](element) node within the `DocumentFragment`, in document order, that matches the specified selectors.

[`DocumentFragment.querySelectorAll()`](documentfragment/queryselectorall)  
Returns a [`NodeList`](nodelist) of all the [`Element`](element) nodes within the `DocumentFragment` that match the specified selectors.

[`DocumentFragment.replaceChildren()`](documentfragment/replacechildren)  
Replaces the existing children of a `DocumentFragment` with a specified new set of children.

<span class="page-not-created">`DocumentFragment.getElementById()`</span>  
Returns the first [`Element`](element) node within the `DocumentFragment`, in document order, that matches the specified ID. Functionally equivalent to [`Document.getElementById()`](document/getelementbyid).

## Usage notes

A common use for `DocumentFragment` is to create one, assemble a DOM subtree within it, then append or insert the fragment into the DOM using [`Node`](node) interface methods such as [`appendChild()`](node/appendchild) or [`insertBefore()`](node/insertbefore). Doing this moves the fragment's nodes into the DOM, leaving behind an empty `DocumentFragment`. Because all of the nodes are inserted into the document at once, only one reflow and render is triggered instead of potentially one for each node inserted if they were inserted separately.

This interface is also of great use with Web components: [`<template>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template) elements contain a `DocumentFragment` in their [`HTMLTemplateElement.content`](htmltemplateelement/content) property.

An empty `DocumentFragment` can be created using the [`document.createDocumentFragment()`](document/createdocumentfragment) method or the constructor.

## Example

### HTML

    <ul id="list"></ul>

### JavaScript

    var list = document.querySelector('#list')
    var fruits = ['Apple', 'Orange', 'Banana', 'Melon']

    var fragment = new DocumentFragment()

    fruits.forEach(function (fruit) {
      var li = document.createElement('li')
      li.innerHTML = fruit
      fragment.appendChild(li)
    })

    list.appendChild(fragment)

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-documentfragment">DOM<br />
<span class="small">The definition of 'DocumentFragment' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the constructor and the implementation of <a href="parentnode"><code>ParentNode</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/selectors-api/#the-apis">Selectors API Level 1<br />
<span class="small">The definition of 'DocumentFragment' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the <code>querySelector()</code> and <code>querySelectorAll()</code> methods.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-B63ED1A3">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'DocumentFragment' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-B63ED1A3">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'DocumentFragment' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-B63ED1A3">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'DocumentFragment' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`DocumentFragment`

1

12

1

9

8

3

1

18

4

10.1

1

1.0

`DocumentFragment`

29

17

24

No

16

8

≤37

29

24

16

8

2.0

`append`

54

17

49

No

41

10

54

54

49

41

10

6.0

`childElementCount`

29

17

25

No

16

9

≤37

29

25

16

9

2.0

`children`

29

16

25

No

16

9

≤37

29

25

16

9

2.0

`firstElementChild`

29

17

25

No

16

9

≤37

29

25

16

9

2.0

`lastElementChild`

29

17

25

No

16

9

≤37

29

25

16

9

2.0

`prepend`

54

17

49

No

41

10

54

54

49

41

10

6.0

`querySelector`

1

12

3.5

9

8

`querySelectorAll()` is supported, but only for CSS 2.1 selectors.

10

4

1

18

4

10.1

3

1.0

`querySelectorAll`

1

12

3.5

9

8

`querySelectorAll()` is supported, but only for CSS 2.1 selectors.

10

4

1

18

4

10.1

3

1.0

`replaceChildren`

86

86

78

No

72

14

86

86

79

61

14

14.0

## See also

- [The DOM interfaces index.](document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment</a>
