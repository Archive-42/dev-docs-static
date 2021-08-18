# Document.applets

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `applets` property of the [`Document`](../document) interface returns a list of the applets within a document.

**Note**: The [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet) element was removed in [Gecko 56](https://bugzilla.mozilla.org/show_bug.cgi?id=1279218) and [Chrome in late 2015](https://bugs.chromium.org/p/chromium/issues/detail?id=470301). Since then, calling `document.applets` in those browsers always returns an empty [`HTMLCollection`](../htmlcollection). Removal is being considered in [WebKit](https://bugs.webkit.org/show_bug.cgi?id=157926) and [Edge](https://developer.microsoft.com/en-us/microsoft-edge/platform/issues/11946645/).

## Syntax

    var nodeList = document.applets;

### Value

An [`HTMLCollection`](../htmlcollection).

## Example

    // When you know the second applet is the one you want
    my_java_app = document.applets[1];

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-applets">HTML Living Standard<br />
<span class="small">The definition of 'Document.applets' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Obsoleted.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-85113862">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'Document.applets' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`applets`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/applets" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/applets</a>
