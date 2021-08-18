# CSSPrimitiveValue.primitiveType

The `primitiveType` read-only property of the [`CSSPrimitiveValue`](../cssprimitivevalue) interface represents the type of a CSS value.

## Syntax

    type = cssPrimitiveValue.primitiveType;

### Value

An `unsigned short` representing the type of the value. Possible values are:

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>CSS_ATTR</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/attr()"><code>attr()</code></a> function. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr><tr class="even"><td><code>CSS_CM</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in centimeters. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_COUNTER</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters/Using_CSS_counters">counter or counters</a> function. The value can be obtained by using the <code>getCounterValue()</code> method.</td></tr><tr class="even"><td><code>CSS_DEG</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in degrees. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_DIMENSION</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number"><code>&lt;number&gt;</code></a> with an unknown dimension. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_EMS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in em units. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_EXS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in ex units. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_GRAD</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in grads. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_HZ</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/frequency"><code>&lt;frequency&gt;</code></a> in Hertz. The value can be obtained by using the getFloatValue method.</td></tr><tr class="even"><td><code>CSS_IDENT</code></td><td>The value is an identifier. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_IN</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in inches. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_KHZ</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/frequency"><code>&lt;frequency&gt;</code></a> in Kilohertz. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_MM</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in millimeters. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_MS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/time"><code>&lt;time&gt;</code></a> in milliseconds. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_NUMBER</code></td><td>The value is a simple <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number"><code>&lt;number&gt;</code></a>. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_PC</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in picas. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_PERCENTAGE</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/percentage"><code>&lt;percentage&gt;</code></a>. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_PT</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in points. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_PX</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in pixels. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_RAD</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in radians. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_RECT</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/shape#syntax"><code>rect()</code></a> function. The value can be obtained by using the <code>getRectValue()</code> method.</td></tr><tr class="even"><td><code>CSS_RGBCOLOR</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value"><code>&lt;color&gt;</code></a>. The value can be obtained by using the <code>getRGBColorValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_S</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/time"><code>&lt;time&gt;</code></a> in seconds. The value can be obtained by using the <code>getFloatValue()</code> method.</td></tr><tr class="even"><td><code>CSS_STRING</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/string"><code>&lt;string&gt;</code></a>. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr><tr class="odd"><td><code>CSS_UNKNOWN</code></td><td>The value is not a recognized CSS2 value. The value can only be obtained by using the <a href="../cssvalue/csstext"><code>cssText</code></a> attribute.</td></tr><tr class="even"><td><code>CSS_URI</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/url()"><code>url()</code></a>. The value can be obtained by using the <code>getStringValue()</code> method.</td></tr></tbody></table>

## Example

    var cs = window.getComputedStyle(document.body);
    var cssValue = cs.getPropertyCSSValue("color");
    console.log(cssValue.primitiveType);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSPrimitiveValue-primitiveType">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSPrimitiveValue.primitiveType' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [`CSSStyleDeclaration.getPropertyCSSValue()`](../cssstyledeclaration/getpropertycssvalue)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/primitiveType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/primitiveType</a>
