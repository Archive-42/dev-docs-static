# CSSRule.parentRule

The `parentRule` property of the [`CSSRule`](../cssrule) interface returns the containing rule of the current rule if this exists, or otherwise returns null.

## Syntax

    var parentRule = cssRule.parentRule

### Values

`parentRule`  
A [`CSSRule`](../cssrule) which is the type of the containing rules. If the current rule is inside a media query, this would return [`CSSMediaRule`](../cssmediarule). Otherwise it returns null.

## Example

    @media (min-width: 500px) {
      .box {
        width: 100px;
        height: 200px;
        background-color: red;
      }

      body {
        color: blue;
      }
    }

    let myRules = document.styleSheets[0].cssRules;
    let childRules = myRules[0].cssRules;
    console.log(childRules[0].parentRule); // a CSSMediaRule

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

`parentRule`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSRule/parentRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSRule/parentRule</a>
