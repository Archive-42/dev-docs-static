# Document.origin

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Use `self.origin` instead.

The `Document.origin` read-only property returns the document's origin. In most cases, this property is equivalent to `document.defaultView.location.origin`.

## Syntax

    var origin = document.origin;

## Examples

    var origin = document.origin;
    // On this page, returns:'https://developer.mozilla.org'

    var origin = document.origin;
    // On "about:blank", returns:'null'

    var origin = document.origin;
    // On "data:text/html,<b>foo</b>", returns:'null'

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

`origin`

41-71

12-79

No

No

28-58

6.1-14

41-71

41-71

No

28-50

6.1-14

4.0-10.0

## See also

- The <span class="page-not-created">`URLUtils.origin`</span> property.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/origin</a>
