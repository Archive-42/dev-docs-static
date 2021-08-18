# CSSNamespaceRule

The `CSSNamespaceRule` interface describes an object representing a single CSS [`@namespace`](https://developer.mozilla.org/en-US/docs/Web/CSS/@namespace) [`at-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule).

## Properties

_Inherits methods from its ancestor [`CSSRule`](cssrule)._

[`CSSNamespaceRule.namespaceURI`](cssnamespacerule/namespaceuri)  
Returns a [`DOMString`](domstring) containing the text of the URI of the given namespace.

[`CSSNamespaceRule.prefix`](cssnamespacerule/prefix)  
Returns a [`DOMString`](domstring) with the name of the prefix associated to this namespace. If there is no such prefix, returns an empty string.

## Methods

_Inherits methods from its ancestor [`CSSRule`](cssrule)._

## Examples

The stylesheet includes a namespace as the only rule. Therefore the first [`CSSRule`](cssrule) returned will be a `CSSNamespaceRule`.

    @namespace url(http://www.w3.org/1999/xhtml);

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0]); //a CSSNamespaceRule

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#the-cssnamespacerule-interface">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSNamespaceRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSNamespaceRule`

47

12

53

9

36

10.1

47

47

53

36

10.3

5.0

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSNamespaceRule</a>
