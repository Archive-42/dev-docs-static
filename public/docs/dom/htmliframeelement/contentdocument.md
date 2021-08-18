HTMLIFrameElement.contentDocument
=================================

If the iframe and the iframe's parent document are [Same Origin](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy), returns a [`Document`](../document) (that is, the active document in the inline frame's nested browsing context), else returns `null`.

Example of contentDocument
--------------------------

    var iframeDocument = document.getElementsByTagName("iframe")[0].contentDocument;

    iframeDocument.body.style.backgroundColor = "blue";
    // This would turn the iframe blue.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-iframe-contentdocument">HTML Living Standard<br />
<span class="small">The definition of 'HTMLIFrameElement: contentDocument' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`contentDocument`

1

12

1

8

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/contentDocument" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/contentDocument</a>
