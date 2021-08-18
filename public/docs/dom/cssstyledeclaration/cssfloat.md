# CSSStyleDeclaration.cssFloat

The `cssFloat` property of the [`CSSStyleDeclaration`](../cssstyledeclaration) interface returns the result of invoking [`CSSStyleDeclaration.getPropertyValue()`](getpropertyvalue) with `float` as an argument.

When setting, it invokes [`CSSStyleDeclaration.setProperty()`](setproperty) with `float` as the first argument, and the given value as the second argument. The given value must be a valid value for the [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float) property.

## Syntax

    var float = CSSStyleDeclaration.cssFloat();
    CSSStyleDeclaration.cssFloat = "right"

### Value

A [`CSSOMString`](../cssomstring).

## Example

In the below example, the stylesheet contains a single rule for `.box`, which has the [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float) property with a value of `left`. This value will be returned by `cssFloat`. We then set the value to "right" using `cssFloat`, and return the new value.

    .box {
      float: left;
      inline-size: 300px;
    }

    let myRules = document.styleSheets[0].cssRules;
    let rule = myRules[0];
    console.log(rule.style.cssFloat); // "left"
    rule.style.cssFloat = "right";
    console.log(rule.style.cssFloat); //right

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstyledeclaration-cssfloat">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleDeclaration.cssFloat' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`cssFloat`

1

12

1-17

9

≤12.1

1

4.4

18

4-17

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/cssFloat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/cssFloat</a>
