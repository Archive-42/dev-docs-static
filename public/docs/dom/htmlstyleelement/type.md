# HTMLStyleElement.type

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `HTMLStyleElement.type` read-only property returns the type of the current style.

For Gecko, the type is most often given as "text/css." From the W3C spec on CSS: "The expectation is that binding-specific casting methods can be used to cast down from an instance of the CSSRule interface to the specific derived interface implied by the type."

## Syntax

    string = style.type;

## Example

    if (newStyle.type != "text/css"){
       // not supported!
       warnCSS();
    }

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

`type`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement/type</a>
