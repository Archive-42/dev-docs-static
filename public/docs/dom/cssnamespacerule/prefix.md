# CSSNamespaceRule.prefix

The read-only `prefix` property of the [`CSSNamespaceRule`](../cssnamespacerule) returns a [`DOMString`](../domstring) with the name of the prefix associated to this namespace. If there is no such prefix, it returns an empty string.

## Syntax

    var prefix = CSSNamespaceRule.prefix

### Returns

A [`DOMString`](../domstring) containing the prefix associated to this namespace. If there is no prefix an empty string.

## Examples

The stylesheet includes two namespace rules. The first has no prefix the second the prefix `svg`. Two `CSSNamespaceRule` objects will be returned. The value of the `prefix` property for the first will be an empty string, for the second `svg`.

    @namespace url(http://www.w3.org/1999/xhtml);
    @namespace svg url(http://www.w3.org/2000/svg);

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].namespaceURI); an empty string ""
    console.log(myRules[1].namespaceURI); "svg"

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

`prefix`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule/prefix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule/prefix</a>
