# CSSMathValue.operator

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSMathValue.operator` read-only property of the [`CSSMathValue`](../cssmathvalue) interface indicates the operator that the current subtype represents. For example, if the current `CSSMathValue` subtype is `CSSMathSum`, this property will return the string `"sum"`.

## Syntax

    var aString = CSSMathValue.operator;

### Value

A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

<table><thead><tr class="header"><th>Interface</th><th>Value</th></tr></thead><tbody><tr class="odd"><td><code>CSSMathSum</code></td><td><code>"sum"</code></td></tr><tr class="even"><td><code>CSSMathProduct</code></td><td><code>"product"</code></td></tr><tr class="odd"><td><code>CSSMathMin</code></td><td><code>"min"</code></td></tr><tr class="even"><td><code>CSSMathMax</code></td><td><code>"max"</code></td></tr><tr class="odd"><td><code>CSSMathClamp</code></td><td><code>"clamp"</code></td></tr><tr class="even"><td><code>CSSMathNegate</code></td><td><code>"negate"</code></td></tr><tr class="odd"><td><code>CSSMathInvert</code></td><td><code>"invert"</code></td></tr></tbody></table>

## Examples

We create an element with a `width` determined using a `calc()` function, then `console.log()` the `operator`.

    <div>My width has a <code>calc()</code> function</div>

We assign a `width` with a calculation

    div {
      width: calc(50% - 0.5vw);
    }

We add the JavaScript

    const styleMap = document.querySelector('div').computedStyleMap();

    console.log( styleMap.get('width') );                   // CSSMathSum {values: CSSNumericArray, operator: "sum"}
    console.log( styleMap.get('width').values );            // CSSNumericArray {0: CSSUnitValue, 1: CSSMathNegate, length: 2}
    console.log( styleMap.get('width').operator );          // 'sum'
    console.log( styleMap.get('width').values[1].operator ) // 'negate'

The `CSSMathValue.operator` returns `sum` for the equation and `negate` for the operator on the second value.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-cssmathvalue-operator">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSMathValue.operator' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`operator`

66

79

No

No

53

No

66

66

No

47

No

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSMathValue/operator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSMathValue/operator</a>
