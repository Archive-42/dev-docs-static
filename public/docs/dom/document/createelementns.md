# Document.createElementNS()

Creates an element with the specified namespace URI and qualified name.

To create an element without specifying a namespace URI, use the [`createElement()`](createelement) method.

## Syntax

    var element = document.createElementNS(namespaceURI, qualifiedName[, options]);

### Parameters

namespaceURI  
A string that specifies the [namespace URI](https://www.w3.org/TR/2004/REC-DOM-Level-3-Core-20040407/glossary.html#dt-namespaceURI) to associate with the element. The [`namespaceURI`](../element/namespaceuri) property of the created element is initialized with the value of namespaceURI. See [Valid Namespace URIs](#important_namespace_uris).

qualifiedName  
A string that specifies the type of element to be created. The <span class="page-not-created">`nodeName`</span> property of the created element is initialized with the value of qualifiedName.

options<span class="badge inline optional">Optional</span>  
An optional `ElementCreationOptions` object containing a single property named `is`, whose value is the tag name for a custom element previously defined using `customElements.define()`. For backwards compatibility with previous versions of the [Custom Elements specification](https://www.w3.org/TR/custom-elements/), some browsers will allow you to pass a string here instead of an object, where the string's value is the custom element's tag name. See [Extending native HTML elements](https://developers.google.com/web/fundamentals/primers/customelements/#extendhtml) for more information on how to use this parameter.

The new element will be given an `is` attribute whose value is the custom element's tag name. Custom elements are an experimental feature only available in some browsers.

### Return value

The new [`Element`](../element).

## Important Namespace URIs

[HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)  
`http://www.w3.org/1999/xhtml`

[SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)  
`http://www.w3.org/2000/svg`

[MathML](https://developer.mozilla.org/en-US/docs/Web/MathML)  
`http://www.w3.org/1998/Math/MathML`

[XUL](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
`http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul`

[XBL](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XBL) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
`http://www.mozilla.org/xbl`

## Example

This creates a new &lt;div&gt; element in the [XHTML](https://developer.mozilla.org/en-US/docs/Glossary/XHTML) namespace and appends it to the vbox element. Although this is not an extremely useful [XUL](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL) document, it does demonstrate the use of elements from two different namespaces within a single document:

    <?xml version="1.0"?>
    <page xmlns="http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul"
          xmlns:html="http://www.w3.org/1999/xhtml"
          title="||Working with elements||"
          onload="init()">

    <script type="application/javascript"><![CDATA[
     let container;
     let newdiv;
     let txtnode;

     function init(){
       container = document.getElementById("ContainerBox");
       newdiv = document.createElementNS("http://www.w3.org/1999/xhtml", "div");
       txtnode = document.createTextNode("This is text that was constructed dynamically with createElementNS and createTextNode then inserted into the document using appendChild.");
       newdiv.appendChild(txtnode);
       container.appendChild(newdiv);
     }

    ]]></script>

     <vbox id="ContainerBox" flex="1">
      <html:div>
       The script on this page will add dynamic content below:
      </html:div>
     </vbox>

    </page>

The example given above uses inline script which is not recommended in XHTML documents. This particular example is actually an XUL document with embedded XHTML, however, the recommendation still applies.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-createelementns">DOM<br />
<span class="small">The definition of 'Document.createElementNS()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createElementNS`

1

12

1

Doesn't conform to the DOM spec for XUL and XHTML documents: `localName` and `namespaceURI` are not set to null on the created element.

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`options`

56

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

≤79

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

50

Firefox accepts a string instead of an object here, but only from version 51 onwards. In version 50, options must be an object.

?

43

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

?

56

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

56

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

50

Firefox accepts a string instead of an object here, but only from version 51 onwards. In version 50, options must be an object.

43

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

?

6.0

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

## See also

- [`document.createElement()`](createelement)
- [`document.createTextNode()`](createtextnode)
- [`Element.namespaceURI`](../element/namespaceuri)
- [Namespaces in XML](https://www.w3.org/TR/1999/REC-xml-names-19990114)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createElementNS" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createElementNS</a>
