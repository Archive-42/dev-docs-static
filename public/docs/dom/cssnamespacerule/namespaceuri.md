# CSSNamespaceRule.namespaceURI

The read-only `namespaceURI` property of the [`CSSNamespaceRule`](../cssnamespacerule) returns a [`DOMString`](../domstring) containing the text of the URI of the given namespace.

## Syntax

    var namespaceURI = CSSNamespaceRule.namespaceURI

### Returns

A [`DOMString`](../domstring) containing a URI.

## Examples

The stylesheet includes a namespace as the only rule. Therefore the first [`CSSRule`](../cssrule) returned will be a `CSSNamespaceRule`. The value of the `namespaceURI` property will be `http://www.w3.org/1999/xhtml`.

    @namespace url(http://www.w3.org/1999/xhtml);

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].namespaceURI); //http://www.w3.org/1999/xhtml

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssnamespacerule-namespaceuri">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'namespaceURI' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`namespaceURI`

47

12

59

9

36

10.1

47

47

59

36

10.3

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule/namespaceURI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule/namespaceURI</a>
