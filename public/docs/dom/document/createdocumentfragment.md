# Document.createDocumentFragment()

Creates a new empty [`DocumentFragment`](../documentfragment) into which DOM nodes can be added to build an offscreen DOM tree.

## Syntax

    var fragment = document.createDocumentFragment();

### Value

A newly created, empty, [`DocumentFragment`](../documentfragment) object, which is ready to have nodes inserted into it.

## Usage notes

`DocumentFragment`s are DOM [`Node`](../node) objects which are never part of the main DOM tree. The usual use case is to create the document fragment, append elements to the document fragment and then append the document fragment to the DOM tree. In the DOM tree, the document fragment is replaced by all its children.

Since the document fragment is _in memory_ and not part of the main DOM tree, appending children to it does not cause page [reflow](https://developers.google.com/speed/articles/reflow?csw=1) (computation of element's position and geometry). Historically, using document fragments could result in [better performance](http://ejohn.org/blog/dom-documentfragments/).

You can also use the `DocumentFragment` constructor to create a new fragment:

    let fragment = new DocumentFragment();

## Example

This example creates a list of major web browsers in a `DocumentFragment`, then adds the new DOM subtree to the document to be displayed.

### HTML

    <ul id="ul">
    </ul>

### JavaScript

    var element  = document.getElementById('ul'); // assuming ul exists
    var fragment = document.createDocumentFragment();
    var browsers = ['Firefox', 'Chrome', 'Opera',
        'Safari', 'Internet Explorer'];

    browsers.forEach(function(browser) {
        var li = document.createElement('li');
        li.textContent = browser;
        fragment.appendChild(li);
    });

    element.appendChild(fragment);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-createdocumentfragment">DOM<br />
<span class="small">The definition of 'Document.createDocumentFragment()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition in the DOM 1 specification.</td></tr></tbody></table>

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

`createDocumentFragment`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- [`document.implementation.createDocument()`](../domimplementation/createdocument)
- [`documentFragment`](../documentfragment)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createDocumentFragment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createDocumentFragment</a>
