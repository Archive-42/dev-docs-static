# DocumentFragment.firstElementChild

The `DocumentFragment.firstElementChild` read-only property returns the document fragment's first child [`Element`](../element), or `null` if there are no child elements.

## Syntax

    // Getter
    element = fragment.firstElementChild;

    // No setter; read-only property

## Example

    let fragment = new DocumentFragment();
    fragment.firstElementChild; // null

    let paragraph = document.createElement('p');
    fragment.appendChild(paragraph);

    fragment.firstElementChild; // <p>

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-firstelementchild">DOM<br />
<span class="small">The definition of 'ParentNode.firstElementChild' in that specification.</span></a></td></tr></tbody></table>

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

## See also

- [`Element.firstElementChild`](../element/firstelementchild)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/firstElementChild" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/firstElementChild</a>
