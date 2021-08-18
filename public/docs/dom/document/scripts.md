# Document.scripts

The `scripts` property of the [`Document`](../document) interface <span class="seosummary">returns a list of the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements in the document.</span> The returned object is an [`HTMLCollection`](../htmlcollection).

## Syntax

    var scriptList = document.scripts;

### Value

An [`HTMLCollection`](../htmlcollection). You can use this just like an array to get all the elements in the list.

## Example

This example looks to see if the page has any [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements.

    let scripts = document.scripts;

    if (scripts.length) {
      alert('This page has scripts!');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-scripts">HTML Living Standard<br />
<span class="small">The definition of 'Document.scripts' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`scripts`

1

12

9

4

≤12.1

3

1

18

9

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/scripts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/scripts</a>
