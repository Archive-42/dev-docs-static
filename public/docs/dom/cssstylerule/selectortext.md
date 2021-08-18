# CSSStyleRule.selectorText

The `selectorText` property of the [`CSSStyleRule`](../cssstylerule) interface gets and sets the selectors associated with the `CSSStyleRule`.

## Syntax

    var text = CSSStyleRule.selectorText;
    CSSStyleRule.selectorText = text;

### Value

A [`CSSOMString`](../cssomstring).

## Example

The CSS includes one style rule. This will be the first [`CSSRule`](../cssrule) returned by `document.styleSheets[0].cssRules`. `myRules[0].selectorText` therefore returns a literal string of the selector, in this case `"h1"`.

    h1 {
      color: pink;
    }

    let text = document.styleSheets[0].selectorText;
    console.log(myRules[0].selectorText); // a string containing "h1".

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstylerule-selectortext">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleRule.selectorText' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`selectorText`

1

12

1

9

≤12.1

1

4.4

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule/selectorText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule/selectorText</a>
