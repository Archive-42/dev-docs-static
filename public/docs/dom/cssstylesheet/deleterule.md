# CSSStyleSheet.deleteRule()

The [`CSSStyleSheet`](../cssstylesheet) method `deleteRule()` removes a rule from the stylesheet object.

## Syntax

    cssStyleSheet.deleteRule(index)

### Parameters

`index`  
The index into the stylesheet's [`CSSRuleList`](../cssrulelist) indicating the rule to be removed.

### Return value

`undefined`

## Example

This example removes the first rule from the stylesheet `myStyles`.

     myStyles.deleteRule(0);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstylesheet-deleterule">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleSheet.deleteRule()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- [CSS Object Model](../css_object_model)
- [Using dynamic styling information](../css_object_model/using_dynamic_styling_information)
- [`insertRule()`](insertrule)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/deleteRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/deleteRule</a>
