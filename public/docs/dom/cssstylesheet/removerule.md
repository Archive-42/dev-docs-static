# CSSStyleSheet.removeRule()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete [`CSSStyleSheet`](../cssstylesheet) method `removeRule()` removes a rule from the stylesheet object. It is functionally identical to the standard, preferred method [`deleteRule()`](deleterule).

**Note:** This is a _legacy method_ which has been replaced by the standard method [`deleteRule()`](deleterule). You should use that instead.

## Syntax

    cssStyleSheet.removeRule(index)

### Parameters

`index`  
The index into the stylesheet's [`CSSRuleList`](../cssrulelist) indicating the rule to be removed.

### Return value

`undefined`

## Example

This example removes the first rule from the stylesheet `myStyles`.

     myStyles.removeRule(0);

You can rewrite this to use the standard `deleteRule()` method very easily:

    myStyles.deleteRule(0);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstylesheet-removerule">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleSheet.removeRule()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`removeRule`

1

12

68

9

15

3

1

18

68

14

1

1.0

## See also

- [CSS Object Model](../css_object_model)
- [Using dynamic styling information](../css_object_model/using_dynamic_styling_information)
- [`insertRule()`](insertrule)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/removeRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/removeRule</a>
