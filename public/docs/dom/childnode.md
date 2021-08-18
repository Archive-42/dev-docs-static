# ChildNode

The `ChildNode` mixin contains methods and properties that are common to all types of [`Node`](node) objects that can have a parent. It's implemented by [`Element`](element), [`DocumentType`](documenttype), and [`CharacterData`](characterdata) objects.

## Properties

_There are neither inherited, nor specific properties._

## Methods

_There are no inherited methods._

[`ChildNode.remove()`](childnode/remove) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Removes this `ChildNode` from the `children` list of its parent.

[`ChildNode.before()`](childnode/before) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Inserts a set of [`Node`](node) or [`DOMString`](domstring) objects in the `children` list of this `ChildNode`'s parent, just before this `ChildNode`. [`DOMString`](domstring) objects are inserted as equivalent [`Text`](text) nodes.

[`ChildNode.after()`](childnode/after) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Inserts a set of [`Node`](node) or [`DOMString`](domstring) objects in the `children` list of this `ChildNode`'s parent, just after this `ChildNode`. [`DOMString`](domstring) objects are inserted as equivalent [`Text`](text) nodes.

[`ChildNode.replaceWith()`](childnode/replacewith) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Replaces this `ChildNode` in the `children` list of its parent with a set of [`Node`](node) or [`DOMString`](domstring) objects. [`DOMString`](domstring) objects are inserted as equivalent [`Text`](text) nodes.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-childnode">DOM<br />
<span class="small">The definition of 'ChildNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Split the <code>ElementTraversal</code> interface in <a href="parentnode"><code>ParentNode</code></a> and <code>ChildNode</code>. <code>previousElementSibling</code> and <code>nextElementSibling</code> are now defined on the latter. The <a href="characterdata"><code>CharacterData</code></a> and <a href="documenttype"><code>DocumentType</code></a> implemented the new interfaces. Added the <code>remove()</code>, <code>before()</code>, <code>after()</code> and <code>replaceWith()</code> methods.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/ElementTraversal/#interface-elementTraversal">Element Traversal Specification<br />
<span class="small">The definition of 'ElementTraversal' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the initial definition of its properties to the <code>ElementTraversal</code> pure interface and use it on <a href="element"><code>Element</code></a>.</td></tr></tbody></table>

## Polyfill

External on GitHub: `childNode.js`

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

`ChildNode`

1

12

23

9

10

4

1

Yes

23

10.1

Yes

Yes

`after`

54

17

49

No

39

10

54

54

49

41

10

6.0

`before`

54

17

49

No

39

10

54

54

49

41

10

6.0

`remove`

23

12

23

No

15

7

≤37

25

23

14

7

1.5

`replaceWith`

54

17

49

No

39

Yes

54

54

49

41

Yes

6.0

## See also

- The [`ParentNode`](parentnode) interface
- Object types implementing the [`ParentNode`](parentnode) interface
  - [`CharacterData`](characterdata)
  - [`Element`](element)
  - [`DocumentType`](documenttype)
- The [`Element`](element) interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ChildNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ChildNode</a>
