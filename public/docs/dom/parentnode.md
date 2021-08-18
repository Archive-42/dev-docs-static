# ParentNode

The `ParentNode` mixin contains methods and properties that are common to all types of [`Node`](node) objects that can have children. It's implemented by [`Element`](element), [`Document`](document), and [`DocumentFragment`](documentfragment) objects.

See [Locating DOM elements using selectors](document_object_model/locating_dom_elements_using_selectors) to learn how to use [CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors) to find nodes or elements of interest.

## Properties

[`ParentNode.childElementCount`](element/childelementcount) <span class="badge inline readonly">Read only </span>  
Returns the number of children of this `ParentNode` which are [`elements`](element).

[`ParentNode.children`](element/children) <span class="badge inline readonly">Read only </span>  
Returns a live [`HTMLCollection`](htmlcollection) containing all of the [`Element`](element) objects that are children of this `ParentNode`, omitting all of its non-element nodes.

[`ParentNode.firstElementChild`](element/firstelementchild) <span class="badge inline readonly">Read only </span>  
Returns the first node which is both a child of this `ParentNode` _and_ is also an `Element`, or `null` if there is none.

[`ParentNode.lastElementChild`](element/lastelementchild) <span class="badge inline readonly">Read only </span>  
Returns the last node which is both a child of this `ParentNode` _and_ is an `Element`, or `null` if there is none.

## Methods

[`ParentNode.append()`](element/append)  
Inserts a set of [`Node`](node) objects or [`DOMString`](domstring) objects after the last child of the `ParentNode`. [`DOMString`](domstring) objects are inserted as equivalent [`Text`](text) nodes.

[`ParentNode.prepend()`](element/prepend)  
Inserts a set of [`Node`](node) objects or [`DOMString`](domstring) objects before the first child of the `ParentNode`. [`DOMString`](domstring) objects are inserted as equivalent [`Text`](text) nodes.

[`ParentNode.querySelector()`](parentnode/queryselector)  
Returns the first [`Element`](element) with the current element as root that matches the specified group of selectors.

[`ParentNode.querySelectorAll()`](parentnode/queryselectorall)  
Returns a [`NodeList`](nodelist) representing a list of elements with the current element as root that matches the specified group of selectors.

[`ParentNode.replaceChildren()`](element/replacechildren)  
Replaces the existing children of a node with a specified new set of children.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#parentnode">DOM<br />
<span class="small">The definition of 'ParentNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Split the <code>ElementTraversal</code> interface into <a href="childnode"><code>ChildNode</code></a> and <a href="parentnode"><code>ParentNode</code></a>. The <a href="element/firstelementchild"><code>ParentNode.firstElementChild</code></a>, <a href="element/lastelementchild"><code>ParentNode.lastElementChild</code></a>, and <a href="element/childelementcount"><code>ParentNode.childElementCount</code></a> properties are now defined on the latter. Added the <a href="element/children"><code>ParentNode.children</code></a> property, and the <a href="parentnode/queryselector"><code>ParentNode.querySelector()</code></a>, <a href="parentnode/queryselectorall"><code>ParentNode.querySelectorAll()</code></a>, <a href="element/append"><code>ParentNode.append()</code></a>, and <a href="element/prepend"><code>ParentNode.prepend()</code></a> methods.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/ElementTraversal/#interface-elementTraversal">Element Traversal Specification<br />
<span class="small">The definition of 'ElementTraversal' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the initial definition of its properties to the <code>ElementTraversal</code> pure interface and used it on <a href="element"><code>Element</code></a>.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.ParentNode`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- The [`ChildNode`](childnode) pure interface.
- Object types implementing this mixin: [`Document`](document), [`Element`](element), and [`DocumentFragment`](documentfragment).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ParentNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ParentNode</a>
