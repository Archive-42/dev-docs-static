# Document.createCDATASection()

`createCDATASection()` creates a new CDATA section node, and returns it.

## Syntax

    var CDATASectionNode = document.createCDATASection(data);

- CDATASectionNode is a [CDATA Section](../cdatasection) node.
- data is a string containing the data to be added to the CDATA Section.

## Example

    var docu = new DOMParser().parseFromString('<xml></xml>', 'application/xml')

    var cdata = docu.createCDATASection('Some <CDATA> data & then some');

    docu.getElementsByTagName('xml')[0].appendChild(cdata);

    alert(new XMLSerializer().serializeToString(docu));
    // Displays: <xml><![CDATA[Some <CDATA> data & then some]]></xml>

## Notes

- This will only work with XML, not HTML documents (as HTML documents do not support CDATA sections); attempting it on an HTML document will throw `NOT_SUPPORTED_ERR`.
- Will throw a `NS_ERROR_DOM_INVALID_CHARACTER_ERR` exception if one tries to submit the closing CDATA sequence ("`]]>`") as part of the data, so unescaped user-provided data cannot be safely used without this method getting this exception ([`createTextNode()`](createtextnode) can often be used in its place).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-createcdatasection">DOM<br />
<span class="small">The definition of 'document.createCDATASection' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createCDATASection`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createCDATASection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createCDATASection</a>
