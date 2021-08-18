# Document.implementation

The `Document.implementation` property returns a [`DOMImplementation`](../domimplementation) object associated with the current document.

## Syntax

    DOMImpObj = document.implementation;

## Example

    var modName = "HTML";
    var modVer = "2.0";
    var conformTest = document.implementation.hasFeature( modName, modVer );

    alert( "DOM " + modName + " " + modVer + " supported?: " + conformTest );

    // alerts with: "DOM HTML 2.0 supported?: true" if DOM Level 2 HTML module is supported.

A list of module names (e.g., Core, HTML, XML, etc.) is available in the DOM Level 2 [Conformance Section](https://www.w3.org/TR/DOM-Level-2-Core/introduction.html#ID-Conformance-h2).

## Notes

The W3C's DOM Level 1 Recommendation only specified the `hasFeature` method, which is one way to determine if a DOM module is supported by a browser (see example above and [What does your user agent claim to support?](https://www.w3.org/2003/02/06-dom-support.html)). If available, other `DOMImplementation` methods provide services for controlling things outside of a single document. For example, the `DOMImplementation` interface includes a `createDocumentType` method with which DTDs can be created for one or more documents managed by the implementation.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-implementation">DOM<br />
<span class="small">The definition of 'document.implementation' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`implementation`

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

### Gecko-specific notes

- Starting with Gecko 19.0 (Firefox 19.0 / Thunderbird 19.0 / SeaMonkey 2.16) the [`hasFeature`](../domimplementation/hasfeature) method will always return true.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/implementation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/implementation</a>
