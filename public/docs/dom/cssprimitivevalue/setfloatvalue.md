# CSSPrimitiveValue.setFloatValue()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `setFloatValue()` method of the [`CSSPrimitiveValue`](../cssprimitivevalue) interface is used to set a float value. If the property attached to this value can't accept the specified unit or the float value, the value will be unchanged and a [`DOMException`](../domexception) will be raised.

## Syntax

    cssPrimitiveValue.setFloatValue(unitType, floatValue);

### Parameters

unitType  
An `unsigned short` representing the code for the unit type, in which the value should be returned. Valid values are:

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>CSS_CM</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in centimeters.</td></tr><tr class="even"><td><code>CSS_DEG</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in degrees.</td></tr><tr class="odd"><td><code>CSS_DIMENSION</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number"><code>&lt;number&gt;</code></a> with an unknown dimension.</td></tr><tr class="even"><td><code>CSS_EMS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in em units.</td></tr><tr class="odd"><td><code>CSS_EXS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in ex units.</td></tr><tr class="even"><td><code>CSS_GRAD</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in grads.</td></tr><tr class="odd"><td><code>CSS_HZ</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/frequency"><code>&lt;frequency&gt;</code></a> in Hertz. The value can be obtained by using the getFloatValue method.</td></tr><tr class="even"><td><code>CSS_IN</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in inches.</td></tr><tr class="odd"><td><code>CSS_KHZ</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/frequency"><code>&lt;frequency&gt;</code></a> in Kilohertz.</td></tr><tr class="even"><td><code>CSS_MM</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in millimeters.</td></tr><tr class="odd"><td><code>CSS_MS</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/time"><code>&lt;time&gt;</code></a> in milliseconds.</td></tr><tr class="even"><td><code>CSS_NUMBER</code></td><td>The value is a simple <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/number"><code>&lt;number&gt;</code></a>.</td></tr><tr class="odd"><td><code>CSS_PC</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in picas.</td></tr><tr class="even"><td><code>CSS_PERCENTAGE</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/percentage"><code>&lt;percentage&gt;</code></a>.</td></tr><tr class="odd"><td><code>CSS_PT</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in points.</td></tr><tr class="even"><td><code>CSS_PX</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length"><code>&lt;length&gt;</code></a> in pixels.</td></tr><tr class="odd"><td><code>CSS_RAD</code></td><td>The value is an <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle"><code>&lt;angle&gt;</code></a> in radians.</td></tr><tr class="even"><td><code>CSS_S</code></td><td>The value is a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/time"><code>&lt;time&gt;</code></a> in seconds.</td></tr></tbody></table>

floatValue  
A `float` representing the new float value.

### Return value

Void.

### Exceptions

<table><thead><tr class="header"><th><strong>Type</strong></th><th><strong>Description</strong></th></tr></thead><tbody><tr class="odd"><td><code>DOMException</code></td><td>An <code>INVALID_ACCESS_ERR</code> is raised if the CSS value doesn't contain a float value or if the string value can't be converted into the specified unit.<br />
An NO_MODIFICATION_ALLOWED_ERR is raised if this property is read-only.</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSPrimitiveValue-setFloatValue">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSPrimitiveValue.setFloatValue' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/setFloatValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/setFloatValue</a>
