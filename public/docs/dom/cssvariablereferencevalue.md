# CSSVariableReferenceValue

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSVariableReferenceValue` interface of the [CSS_Object_Model\#css_typed_object_model](css_object_model#css_typed_object_model) allows you to create a custom name for a built-in CSS value. This object functionality is sometimes called a "CSS variable" and serves the same purpose as the [`var()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/var()>) function. The custom name must begin with two dashes.

## Constructor

[`CSSVariableReferenceValue.CSSVariableReferenceValue()`](cssvariablereferencevalue/cssvariablereferencevalue)  
Creates a new `CSSVariableReferenceValue` object.

## Properties

[`CSSVariableReferenceValue.variable`](cssvariablereferencevalue/variable)  
Returns the custom name passed to the constructor.

[`CSSVariableReferenceValue.fallback`](cssvariablereferencevalue/fallback) <span class="badge inline readonly">Read only </span>  
Returns the built-in CSS value for the custom name.

## Methods

None.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#cssvariablereferencevalue">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSVariableReferenceValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSVariableReferenceValue`

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

`CSSVariableReferenceValue`

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

`fallback`

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

`variable`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSVariableReferenceValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSVariableReferenceValue</a>
