# CSSValueList.item()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `item()` method of the [`CSSValueList`](../cssvaluelist) interface is used to retrieve a [`CSSValue`](../cssvalue) by ordinal index.

The order in this collection represents the order of the values in the CSS style property. If the index is greater than or equal to the number of values in the list, this method returns `null`.

## Syntax

    var cssValue = cssValueList.item(index);

### Parameters

index  
An `unsigned long` representing the index of the CSS value within the collection.

### Return value

A [`CSSValue`](../cssvalue) object at the `index` position in the `CSSValueList`, or `null` if that is not a valid index.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSValueList-item">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSValueList.item' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`item`

No

No

1-62

No

No

3

No

No

4-62

?

1

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList/item" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList/item</a>
