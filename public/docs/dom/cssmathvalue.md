# CSSMathValue

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSMathValue` interface of the [CSS_Object_Model\#css_typed_object_model](css_object_model#css_typed_object_model) a base class for classes representing complex numeric values.

## Interfaces based on CSSMathValue

Below is a list of interfaces based on the CSSMathValue interface.

- [`CSSMathInvert`](cssmathinvert)
- [`CSSMathMax`](cssmathmax)
- [`CSSMathMin`](cssmathmin)
- [`CSSMathNegate`](cssmathnegate)
- [`CSSMathProduct`](cssmathproduct)
- [`CSSMathSum`](cssmathsum)

## Properties

[`CSSMathValue.operator`](cssmathvalue/operator)  
Indicates the operator that the current subtype represents.

### Event handlers

No

## Methods

None.

## Examples

We create an element with a `width` determined using a `calc()` function, then `console.log()` the `operator`.

    <div>has width</div>

We assign a `width` with a calculation

    div {
      width: calc(30% - 20px);
    }

We add the JavaScript

    const styleMap = document.querySelector('div').computedStyleMap();

    console.log( styleMap.get('width') );                  // CSSMathSum {values: CSSNumericArray, operator: "sum"}
    console.log( styleMap.get('width').operator );         // 'sum'
    console.log( styleMap.get('width').values[1].value );  // -20

The `CSSMathValue.operator` returns '`sum`' because `styleMap.get('width').values[1].value );` is `-20`: adding a negative number.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#complex-numeric">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSMathValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSMathValue`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSMathValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSMathValue</a>
