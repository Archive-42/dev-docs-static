ProcessingInstruction
=====================

The `ProcessingInstruction` interface represents a [processing instruction](https://www.w3.org/TR/xml/#sec-pi); that is, a [`Node`](node) which embeds an instruction targeting a specific application but that can be ignored by any other applications which don't recognize the instruction.

A processing instruction is different from the [XML declaration](https://developer.mozilla.org/en-US/docs/Web/XML/XML_introduction#xml_declaration).

User-defined processing instructions cannot begin with "`xml`", as `xml`-prefixed processing-instruction target names are reserved by the XML specification for particular, standard uses (see, for example, `<?xml-stylesheet ?>`).

The `ProcessingInstruction` interface inherits methods and properties from [`Node`](node).

Properties
----------

 `target` ([`DOMString`](domstring)) <span class="badge inline readonly">Read only </span>   
A name identifying the application to which the instruction is targeted.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#processinginstruction">DOM<br />
<span class="small">The definition of 'ProcessingInstruction' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/xml/#sec-pi">XML specification</a></td><td></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`ProcessingInstruction`

1

12

Yes

?

≤12.1

Yes

1

18

Yes

≤12.1

Yes

1.0

`data`

1

≤79

Yes

?

≤12.1

Yes

1

18

Yes

≤12.1

Yes

1.0

`target`

1

12

Yes

?

≤12.1

Yes

1

18

Yes

≤12.1

Yes

1.0

See also
--------

-   [document.createProcessingInstruction](document/createprocessinginstruction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction</a>
