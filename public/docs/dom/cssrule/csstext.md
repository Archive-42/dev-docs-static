# CSSRule.cssText

The `cssText` property of the [`CSSRule`](../cssrule) interface returns the actual text of a [`CSSStyleSheet`](../cssstylesheet) style-rule.

**Note:** Do not confuse this property with element-style [`CSSStyleDeclaration.cssText`](../cssstyledeclaration/csstext).

Be aware that this property can no longer be set directly, as it is [now specified](https://www.w3.org/TR/cssom-1/#changes-from-5-december-2013) to be _functionally_ modify-only, and silently so. In other words, attempting to set it _does absolutely nothing_, and doesn't even omit a warning or error. Furthermore, it has no settable sub-properties. Therefore, to modify it, use the stylesheet's [`cssRules`](../cssrulelist)`[index]` properties [`.selectorText`](../cssstylerule/selectortext) and [`.style`](../cssstylerule/style) (or its sub-properties). See [Using dynamic styling information](../css_object_model/using_dynamic_styling_information) for details.

## Syntax

    string = cssRule.cssText

## Example

    body {
      background-color: darkblue;
    }

    let stylesheet = document.styleSheets[0];
    console.log(stylesheet.cssRules[0].cssText); // body { background-color: darkblue; }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssrule-csstext">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSRule: cssText' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`cssText`

1

12

1

9

The property normalizes rules and does not return the original verbatim rule text. For example, `border-width: 1px; border-style:solid; border-color:white;` returns `border: 1px solid white;`.

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSRule/cssText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSRule/cssText</a>
