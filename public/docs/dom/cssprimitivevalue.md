# CSSPrimitiveValue

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `CSSPrimitiveValue` interface derives from the [`CSSValue`](cssvalue) interface and represents the current computed value of a CSS property.

This interface represents a single CSS value. It may be used to determine the value of a specific style property currently set in a block or to set a specific style property explicitly within the block. An instance of this interface might be obtained from the [`getPropertyCSSValue()`](cssstyledeclaration/getpropertycssvalue) method of the [`CSSStyleDeclaration`](cssstyledeclaration) interface. A `CSSPrimitiveValue` object only occurs in a context of a CSS property.

Conversions are allowed between absolute values (from millimeters to centimeters, from degrees to radians, and so on) but not between relative values. (For example, a pixel value cannot be converted to a centimeter value.) Percentage values can't be converted since they are relative to the parent value (or another property value). There is one exception for color percentage values: since a color percentage value is relative to the range 0-255, a color percentage value can be converted to a number (see also the <span class="page-not-created">`RGBColor`</span> interface).

## Properties

_Inherits properties from its parent, `CSSValue`_.

[`CSSPrimitiveValue.primitiveType`](cssprimitivevalue/primitivetype) <span class="badge inline readonly">Read only </span>  
An `unsigned short` representing the type of the value. Possible values are:

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>CSS_ATTR</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/attr()"><code>attr()</code></a> function. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr><tr class="even"><td><code>CSS_CM</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in centimeters. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_COUNTER</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters/Using_CSS_counters">counter or counters</a> function. The value can be obtained by using the <code>getCounterValue()</code> method.</td></tr><tr class="even"><td><code>CSS_DEG</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in degrees. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_DIMENSION</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number"><code>&lt;number&gt;</code></a> with an unknown dimension. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_EMS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in em units. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_EXS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in ex units. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_GRAD</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in grads. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_HZ</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/frequency"><code>&lt;frequency&gt;</code></a> in Hertz. The value can be obtained by using the getFloatValue method.</td></tr><tr class="even"><td><code>CSS_IDENT</code></td><td>The value is an identifier. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_IN</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in inches. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_KHZ</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/frequency"><code>&lt;frequency&gt;</code></a> in Kilohertz. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_MM</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in millimeters. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_MS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/time"><code>&lt;time&gt;</code></a> in milliseconds. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_NUMBER</code></td><td>The value is a simple <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number"><code>&lt;number&gt;</code></a>. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_PC</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in picas. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_PERCENTAGE</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/percentage"><code>&lt;percentage&gt;</code></a>. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_PT</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in points. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_PX</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in pixels. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_RAD</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in radians. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_RECT</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/shape#syntax"><code>rect()</code></a> function. The value can be obtained by using the <code>getRectValue()</code> method.</td></tr><tr class="even"><td><code>CSS_RGBCOLOR</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value"><code>&lt;color&gt;</code></a>. The value can be obtained by using the <code>getRGBColorValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_S</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/time"><code>&lt;time&gt;</code></a> in seconds. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_STRING</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/string"><code>&lt;string&gt;</code></a>. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_UNKNOWN</code></td><td>The value is not a recognized CSS2 value. The value can only be obtained by using the <a href="cssvalue/csstext"><code>cssText</code></a> attribute.</td></tr><tr class="even"><td><code>CSS_URI</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/url()"><code>url()</code></a>. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr></tbody></table>

## Methods

[`CSSPrimitiveValue.getCounterValue()`](cssprimitivevalue/getcountervalue)  
This method is used to get the [counter](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters/Using_CSS_counters) value. If this CSS value doesn't contain a counter value, a [`DOMException`](domexception) is raised. Modification to the corresponding style property can be achieved using the <span class="page-not-created">`Counter`</span> interface.

[`CSSPrimitiveValue.getFloatValue()`](cssprimitivevalue/getfloatvalue)  
This method is used to get a float value in a specified unit. If this CSS value doesn't contain a float value or can't be converted into the specified unit, a [`DOMException`](domexception) is raised.

[`CSSPrimitiveValue.getRGBColorValue()`](cssprimitivevalue/getrgbcolorvalue)  
This method is used to get the RGB color. If this CSS value doesn't contain a RGB color value, a [`DOMException`](domexception) is raised. Modification to the corresponding style property can be achieved using the <span class="page-not-created">`RGBColor`</span> interface.

[`CSSPrimitiveValue.getRectValue()`](cssprimitivevalue/getrectvalue)  
This method is used to get the Rect value. If this CSS value doesn't contain a rect value, a [`DOMException`](domexception) is raised. Modification to the corresponding style property can be achieved using the <span class="page-not-created">`Rect`</span> interface.

[`CSSPrimitiveValue.getStringValue()`](cssprimitivevalue/getstringvalue)  
This method is used to get the string value. If the CSS value doesn't contain a string value, a [`DOMException`](domexception) is raised.

[`CSSPrimitiveValue.setFloatValue()`](cssprimitivevalue/setfloatvalue)  
A method to set the float value with a specified unit. If the property attached with this value can not accept the specified unit or the float value, the value will be unchanged and a [`DOMException`](domexception) will be raised.

[`CSSPrimitiveValue.setStringValue()`](cssprimitivevalue/setstringvalue)  
A method to set the string value with the specified unit. If the property attached to this value can't accept the specified unit or the string value, the value will be unchanged and a [`DOMException`](domexception) will be raised.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSPrimitiveValue">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSPrimitiveValue' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`CSSPrimitiveValue`

1-40

No

1-62

No

≤12.1-27

3

1-40

18-40

4-62

≤12.1-27

1

1.0-4.0

`getCounterValue`

1-40

No

20-62

No

15-27

3

1-40

18-40

20-62

14-27

1

1.0-4.0

`getFloatValue`

1-40

No

20-62

No

≤12.1-27

3

1-40

18-40

20-62

≤12.1-27

1

1.0-4.0

`getRectValue`

1-40

No

20-62

No

15-27

3

1-40

18-40

20-62

14-27

1

1.0-4.0

`getRGBColorValue`

1-40

No

20-62

No

15-27

3

1-40

18-40

20-62

14-27

1

1.0-4.0

`getStringValue`

1-40

No

20-62

No

15-27

3

1-40

18-40

20-62

14-27

1

1.0-4.0

`primitiveType`

No

No

20-62

No

No

7

No

No

20-62

No

7

No

`setFloatValue`

1-40

No

20-62

No

15-27

3

1-40

18-40

20-62

14-27

1

1.0-4.0

`setStringValue`

1-40

No

20-62

No

15-27

3

1-40

18-40

20-62

14-27

1

1.0-4.0

## See also

- [`CSSValue`](cssvalue)
- [`CSSValueList`](cssvaluelist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue</a>
