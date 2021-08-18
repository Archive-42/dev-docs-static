# CSSGroupingRule.deleteRule()

The `deleteRule()` method of the [`CSSGroupingRule`](../cssgroupingrule) interface removes a CSS rule from a list of child CSS rules.

## Syntax

    cssGroupingRule.deleteRule(index);

### Parameters

index  
The index of the rule to delete.

### Return value

undefined

### Exceptions

A [`DOMException`](../domexception) IndexSizeError  
Thrown if index is greater than or equal to the number of child CSS rules.

A [`DOMException`](../domexception) InvalidStateError  
Thrown if the rule being removed is an `@namespace` at-rule, and the list of child CSS rules contains anything other than `@import` at-rules and `@namespace` at-rules.

## Examples

    let myRules = document.styleSheets[0].cssRules;
    myRules[0].deleteRule(2); /* deletes the rule at index 2 */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssgroupingrule-deleterule">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'deleteRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`deleteRule`

45

12

20

No

32

No

45

45

20

32

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule/deleteRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule/deleteRule</a>
