# CSSRule.parentStyleSheet

The `parentStyleSheet` property of the [`CSSRule`](../cssrule) interface returns the [`StyleSheet`](../stylesheet) object in which the current rule is defined.

## Syntax

    var stylesheet = cssRule.parentStyleSheet

### Values

`stylesheet`  
A [`StyleSheet`](../stylesheet) object.

## Example

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules.parentStyleSheet);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssrule-parentstylesheet">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSRule: parentStyleSheet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`parentStyleSheet`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSRule/parentStyleSheet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSRule/parentStyleSheet</a>
