# CSSValueList

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `CSSValueList` interface derives from the [`CSSValue`](cssvalue) interface and provides the abstraction of an ordered collection of CSS values.

Some properties allow an empty list in their syntax. In that case, these properties take the `none` identifier. So, an empty list means that the property has the value `none`.

The items in the `CSSValueList` are accessible via an integral index, starting from 0.

## Properties

_Inherits properties from its parent, [`CSSValue`](cssvalue)_.

[`CSSValueList.length`](cssvaluelist/length)<span class="badge inline readonly">Read only </span>  
An `unsigned long` representing the number of `CSSValues` in the list.

## Methods

[`CSSValueList.item()`](cssvaluelist/item)  
This method is used to retrieve a [`CSSValue`](cssvalue) by ordinal index. The order in this collection represents the order of the values in the CSS style property. If index is greater than or equal to the number of values in the list, this returns `null`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSValuesList">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSValuesList' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`CSSValueList`

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

`length`

No

No

1-62

No

No

10

No

No

4-62

?

10

No

## See also

- [`CSSPrimitiveValue`](cssprimitivevalue)
- [`CSSValue`](cssvalue)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSValueList</a>
