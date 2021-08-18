# Document.links

The `links` read-only property of the [`Document`](../document) interface returns a collection of all [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) elements and [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) elements in a document with a value for the [href](../urlutils.href) attribute.

## Syntax

    nodeList = document.links

### Value

An [`HTMLCollection`](../htmlcollection).

## Example

    var links = document.links;
    for(var i = 0; i < links.length; i++) {
      var linkHref = document.createTextNode(links[i].href);
      var lineBreak = document.createElement("br");
      document.body.appendChild(linkHref);
      document.body.appendChild(lineBreak);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-links">HTML Living Standard<br />
<span class="small">The definition of 'Document.links' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-7068919">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'document.links' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`links`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/links" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/links</a>
