# CSSPrimitiveValue.getCounterValue()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `getCounterValue()` method of the [`CSSPrimitiveValue`](../cssprimitivevalue) interface is used to get the [counter](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters/Using_CSS_counters) value. If this CSS value doesn't contain a counter value, a [`DOMException`](../domexception) is raised. Modification to the corresponding style property can be achieved using the <span class="page-not-created">`Counter`</span> interface.

## Syntax

    var counterValue = cssPrimitiveValue.getCounterValue();

### Return value

A <span class="page-not-created">`Counter`</span> object representing the counter value.

### Exceptions

<table><thead><tr class="header"><th><strong>Type</strong></th><th><strong>Description</strong></th></tr></thead><tbody><tr class="odd"><td><code>DOMException</code></td><td>An <code>INVALID_ACCESS_ERR</code> is raised if the CSS value doesn't contain a <code>Counter</code> value (e.g. this is not <code>CSS_COUNTER</code>).</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSPrimitiveValue-getCounterValue">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSPrimitiveValue.getCounterValue' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getCounterValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPrimitiveValue/getCounterValue</a>
