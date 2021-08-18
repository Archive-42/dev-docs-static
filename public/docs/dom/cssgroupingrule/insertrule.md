# CSSGroupingRule.insertRule()

The `insertRule()` method of the [`CSSGroupingRule`](../cssgroupingrule) interface adds a new CSS rule to a list of CSS rules.

## Syntax

    var index = cssGroupingRule.insertRule(rule, index);

### Parameters

rule  
A [`CSSOMString`](../cssomstring)

index<span class="badge inline optional">Optional</span>  
An optional index at which to insert the rule; defaults to 0.

### Return value

The index of the new rule.

### Exceptions

A [`DOMException`](../domexception) IndexSizeError  
Thrown if index is greater than the number of child CSS rules.

A [`DOMException`](../domexception) HierarchyRequestError  
Thrown if, due to constraints specified by CSS, the new rule cannot be inserted into the list at the (zero-index) index position given.

A [`DOMException`](../domexception) InvalidStateError  
Thrown if the new rule is an `@namespace` at-rule, and the list of child CSS rules contains anything other than `@import` at-rules and `@namespace` at-rules.

## Examples

    let myRules = document.styleSheets[0].cssRules;
    myRules[0].insertRule('html {background-color: blue;}',0); /* inserts a rule for the html element at position 0 */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssgroupingrule-insertrule">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'insertRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`insertRule`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule/insertRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule/insertRule</a>
