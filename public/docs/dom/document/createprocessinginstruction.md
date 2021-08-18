# Document.createProcessingInstruction()

`createProcessingInstruction()` generates a new [processing instruction](../processinginstruction) node and returns it.

The new node usually will be inserted into an XML document in order to accomplish anything with it, such as with [`node.insertBefore`](../node/insertbefore).

## Syntax

    piNode = document.createProcessingInstruction(target, data)

### Parameters

- `piNode` is the resulting [`ProcessingInstruction`](../processinginstruction) node.
- `target` is a string containing the first part of the processing instruction (i.e., `<?target … ?>`)
- `data` is a string containing any information the processing instruction should carry, after the target. The data is up to you, but it can't contain `?>`, since that closes the processing instruction.

### Exceptions

`DOM_INVALID_CHARACTER`  
Throws if either of the following are true:

- The processing instruction `target` is invalid — it should be a valid _[XML name](https://www.w3.org/TR/REC-xml/#dt-name)_ that doesn't contain "xml", "XML", or any case combination of the two, other than standardized ones such as `<?xml-stylesheet ?>`.
- The _closing processing instruction sequence_ (`?>`) is part of the `data`.

## Example

    var doc = new DOMParser().parseFromString('<foo />', 'application/xml');
    var pi = doc.createProcessingInstruction('xml-stylesheet', 'href="mycss.css" type="text/css"');

    doc.insertBefore(pi, doc.firstChild);

    console.log(new XMLSerializer().serializeToString(doc));
    // Displays: <?xml-stylesheet href="mycss.css" type="text/css"?><foo/>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-createprocessinginstruction">DOM<br />
<span class="small">The definition of 'createProcessingInstruction()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#dom-document-createprocessinginstruction">DOM4<br />
<span class="small">The definition of 'createProcessingInstruction()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added more explicit definition of how the <code>data</code> parameter is validated.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-135944439">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'createProcessingInstruction()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added note that the namespace of the target name is not checked whether it is well-formed, defined what is considered an illegal character for the target name and specified the returned <a href="../processinginstruction"><code>ProcessingInstruction</code></a> object more precisely.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-135944439">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'createProcessingInstruction()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-135944439">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'createProcessingInstruction()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`createProcessingInstruction`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createProcessingInstruction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createProcessingInstruction</a>
