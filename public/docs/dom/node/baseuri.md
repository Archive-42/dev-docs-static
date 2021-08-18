# Node.baseURI

The `baseURI` read-only property returns the absolute base URL of a [`Node`](../node).

The base URL is used to resolve relative URLs when the browser needs to obtain an absolute URL, for example when processing the HTML [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element's `src` attribute or XML `xlink:href` attribute.

In most cases the base URL is the location of the document, but it can be affected by many factors, including the [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base) element in HTML and the `xml:base` attribute in XML.

## Syntax

    var nodeBaseURI = node.baseURI;

### Value

A [`DOMString`](../domstring) representing the base URL of the specified [`Node`](../node). It may be `null` if unable to obtain an absolute URI. Although this property is read-only, its value may change in certain situations (see below).

## Details

### The base URL of a document

The base URL of a _document_ defaults to the document's address (as displayed by the browser and available in [`window.location`](../window/location)), but it can be changed:

- When an HTML [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base) tag is found in the document
- When the document is new (created dynamically)

See the [Base URLs section of the HTML Living standard](https://developers.whatwg.org/urls.html#base-urls) for details.

You can use `document`.baseURI to obtain the base URL of a document. Note that obtaining the base URL for a document may return different URLs over time if the [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base) tags or the document's location change.

### The base URL of an element

The base URL of an _element_ in HTML normally equals the base URL of the document the node is in.

If the document contains `xml:base` attributes (which you shouldn't do in HTML documents), the `element.baseURI` takes the `xml:base` attributes of element's parents into account when computing the base URL. See [xml:base](https://developer.mozilla.org/en-US/docs/Web/XML/xml:base) for details.

You can use `element`.baseURI to obtain the base URL of an element.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-baseuri">DOM<br />
<span class="small">The definition of 'Node: baseURI' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`baseURI`

1

12

1

No

≤12.1

7

1

18

4

≤12.1

7

1.0

## See also

- [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base) element (HTML)
- `xml:base` attribute (XML documents).
- [`Node.baseURIObject`](../node) - a variant of this API for Mozilla add-ons and internal code. Returns the base URL as an <span class="page-not-created">`nsIURI`</span>.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/baseURI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/baseURI</a>
