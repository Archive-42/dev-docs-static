# CSSMathSum

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSMathSum` interface of the [CSS_Object_Model\#css_typed_object_model](css_object_model#css_typed_object_model) represents the result obtained by calling [`add()`](cssnumericvalue/add), [`sub()`](cssnumericvalue/sub), or [`toSum()`](cssnumericvalue/tosum) on [`CSSNumericValue`](cssnumericvalue).

A CSSMathSum is the object type returned when the `StylePropertyMapReadOnly.get()` method is used on a CSS property whose value is created with a `calc()` function.

## Constructor

[`CSSMathSum.CSSMathSum()`](cssmathsum/cssmathsum)  
Creates a new `CSSMathSum` object.

## Properties

[`CSSMathSum.values`](cssmathsum/values)  
Returns a [`CSSNumericArray`](cssnumericarray) object which contains one or more [`CSSNumericValue`](cssnumericvalue) objects.

### Event handlers

No

## Methods

None.

## Examples

We create an element with a `width` determined using a `calc()` function, then `console.log()` the `operator` and `values`, and dig into the values a bit.

    <div>has width</div>

We assign a `width`

    div {
      width: calc(30% - 20px);
    }

We add the JavaScript

    const styleMap = document.querySelector('div').computedStyleMap();

    console.log( styleMap.get('width') );                  // CSSMathSum {values: CSSNumericArray, operator: "sum"}
    console.log( styleMap.get('width').operator );         // 'sum'
    console.log( styleMap.get('width').values );           // CSSNumericArray {0: CSSUnitValue, 1: CSSUnitValue, length: 2}
    console.log( styleMap.get('width').values[0] );        // CSSUnitValue {value: 30, unit: "percent"}
    console.log( styleMap.get('width').values[0].value );  // 30
    console.log( styleMap.get('width').values[0].unit );   // 'percent'
    console.log( styleMap.get('width').values[1] );        // CSSUnitValue {value: -20, unit: "px"}
    console.log( styleMap.get('width').values[1].value );  //  -20
    console.log( styleMap.get('width').values[1].unit );   // 'px'

The specification is still evolving. In the future we may write the last three lines as:

    console.log( styleMap.get('width').values[1] );            // CSSMathNegate {value: CSSUnitValue, operator: "negate"}
    console.log( styleMap.get('width').values[1].value );      // CSSUnitValue {value: 20, unit: "px"}
    console.log( styleMap.get('width').values[1].value.unit ); // 'px'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#cssmathsum">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSMathSum' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSMathSum`

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

`CSSMathSum`

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

`values`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSMathSum" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSMathSum</a>
