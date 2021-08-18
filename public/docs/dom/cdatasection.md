# CDATASection

The `CDATASection` interface represents a CDATA section that can be used within XML to include extended portions of unescaped text. The symbols `<` and `&` don’t need escaping as they normally do when inside a CDATA section.

In XML, a CDATA section looks like:

    <![CDATA[ ... ]]>

For example:

    <foo>Here is a CDATA section: <![CDATA[ < > & ]]> with all kinds of unescaped text.</foo>

The only sequence which is not allowed within a CDATA section is the closing sequence of a CDATA section itself, `]]>`:

    <![CDATA[ ]]> will cause an error ]]>

Note that CDATA sections should not be used within HTML; they only work in XML.

## Properties

_This interface has no specific properties and implements those of its parent [`Text`](text)._

## Methods

_This interface has no specific methods and implements those of its parent [`Text`](text)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-cdatasection">DOM<br />
<span class="small">The definition of 'CDATASection' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Re-added in <a href="https://github.com/whatwg/dom/pull/295">issue #295</a> due to web breakage</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#cdatasection">DOM4<br />
<span class="small">The definition of 'CDATASection' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Removed in favor of the more generic <a href="text"><code>Text</code></a> interface</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-667469212">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'CDATASection' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-667469212">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'CDATASection' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-667469212">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'CDATASection' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`CDATASection`

1

12

Yes

Yes

Yes

3

≤37

18

4

Yes

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CDATASection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CDATASection</a>
