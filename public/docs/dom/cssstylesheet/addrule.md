# CSSStyleSheet.addRule()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete [`CSSStyleSheet`](../cssstylesheet) interface's `addRule()` _legacy method_ adds a new rule to the stylesheet. You should avoid using this method, and should instead use the more standard [`insertRule()`](insertrule) method.

## Syntax

    var result = cssStyleSheet.addRule(selector, styleBlock, index);

### Parameters

`selector`  
A [`DOMString`](../domstring) specifying the selector portion of the CSS rule. The default is the string `undefined`.

`styleBlock`  
A [`DOMString`](../domstring) indicating the style block to apply to elements matching the `selector`. The default is the string `undefined`.

`index` <span class="badge inline optional">Optional</span>  
An optional index into the stylesheet's [`CSSRuleList`](../cssrulelist) at which to insert the new rule. If `index` is not specified, the next index after the last item currently in the list is used (that is, the value of `cssStyleSheet.cssRules.length`).

### Return value

Always returns -1.

Note that due to somewhat estoteric rules about where you can legally insert rules, it's possible that an exception may be thrown. See [`insertRule()`](insertrule) for more information.

## Usage notes

This method is implemented by browsers by constructing a string using the template literal `` `${selector}{${styleBlock}}` ``, then passing it into the standard [`insertRule()`](insertrule) method.

Therefore, given existing code such as the following:

    cssStyleSheet.addRule(selector, styles, 0);

You can rewrite this to use the more standard `insertRule()` like this:

    cssStyleSheet.insertRule(`${selector} {${styles}}`, 0);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstylesheet-addrule">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleSheet.addRule()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`addRule`

1

12

68

9

15

1

1

18

68

14

1

1.0

## See also

- [CSS Object Model](../css_object_model)
- [Using dynamic styling information](../css_object_model/using_dynamic_styling_information)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/addRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/addRule</a>
