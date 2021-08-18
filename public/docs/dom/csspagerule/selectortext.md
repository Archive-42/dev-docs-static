# CSSPageRule.selectorText

The `selectorText` property of the [`CSSPageRule`](../csspagerule) interface gets and sets the selectors associated with the `CSSPageRule`.

## Syntax

    var text = CSSPageRule.selectorText;
    CSSPageRule.selectorText = text;

### Value

A [`CSSOMString`](../cssomstring).

## Examples

The stylesheet includes two [`@page`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page) rules. The `selectorText` property will return the literal selector text of `:first` as a string.

    @page {
      margin: 1cm;
    }

    @page :first {
      margin: 2cm;
    }

    let myRules = document.styleSheets[0].cssRules; //returns two myRules
    console.log(myRules[1].selectorText); // returns the string ":first"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-csspagerule-selectortext">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSPageRule.selectorText' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes from <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSPageRule">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSPageRule' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

No

9

≤12.1

3

1

18

No

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPageRule/selectorText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPageRule/selectorText</a>
