Element.children
================

The read-only `children` property returns a live [`HTMLCollection`](../htmlcollection) which contains all of the child [`elements`](../element) of the element upon which it was called.

`Element.children` includes only element nodes. To get all child nodes, including non-element nodes like text and comment nodes, use [`Node.childNodes`](../node/childnodes).

Syntax
------

    // Getter
    collection = myElement.children;

    // No setter; read-only property

### Return value

An [`HTMLCollection`](../htmlcollection) which is a live, ordered collection of the DOM elements which are children of `node`. You can access the individual child nodes in the collection by using either the [`item()`](../htmlcollection/item) method on the collection, or by using JavaScript array-style notation.

If the element has no element children, then `children` is an empty list with a `length` of `0`.

Example
-------

    const myElement = document.getElementById('foo');
    for (let i = 0; i < myElement.children.length; i++) {
      console.log(myElement.children[i].tagName);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-children">DOM<br />
<span class="small">The definition of 'ParentNode.children' in that specification.</span></a></td></tr></tbody></table>

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

`children`

1

12

3.5

9

6-9

Also includes non-standard `HTMLCommentElement` nodes.

10

4

1

18

4

10.1

3

1.0

See also
--------

-   [`Node.childNodes`](../node/childnodes)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/children" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/children</a>
