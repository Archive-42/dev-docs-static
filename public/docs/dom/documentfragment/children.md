# DocumentFragment.children

The read-only `children` property returns a live [`HTMLCollection`](../htmlcollection) which contains all of the child [`elements`](../element) of the document fragment upon which it was called.

## Syntax

    // Getter
    collection = myFragment.children;

    // No setter; read-only property

### Return value

An [`HTMLCollection`](../htmlcollection) which is a live, ordered collection of the DOM elements which are children of the document fragment. You can access the individual child nodes in the collection by using either the [`item()`](../htmlcollection/item) method on the collection, or by using JavaScript array-style notation.

If the document fragment has no element children, then `children` is an empty list with a `length` of `0`.

## Example

    let fragment = new DocumentFragment()
    fragment.children; // HTMLCollection []

    let paragraph = document.createElement('p')
    fragment.appendChild(paragraph)

    fragment.children; // HTMLCollection [<p>]

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-children">DOM<br />
<span class="small">The definition of 'ParentNode.children' in that specification.</span></a></td></tr></tbody></table>

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

## See also

- [`Node.childNodes`](../node/childnodes)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/children" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/children</a>
