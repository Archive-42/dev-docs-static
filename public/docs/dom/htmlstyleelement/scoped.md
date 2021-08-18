# HTMLStyleElement.scoped

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `HTMLStyleElement.scoped` property is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating if the element applies to the whole document (`false`) or only to the parent's sub-tree (`true`).

By default it contains the value of the [`scoped`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style#attr-scoped) content attribute.

## Syntax

    value = style.scoped;
    style.scoped = true;

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

`scoped`

19-35

No

55-61

This property was hidden behind a pref because no other browsers support it (See [bug 1291515](https://bugzil.la/1291515)).

21-55

No

No

No

No

No

55-61

This property was hidden behind a pref because no other browsers support it (See [bug 1291515](https://bugzil.la/1291515)).

21-55

No

No

No

## See also

- The [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) HTML Element.
- The [`:scope`](https://developer.mozilla.org/en-US/docs/Web/CSS/:scope) CSS pseudo-class.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement/scoped" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement/scoped</a>
