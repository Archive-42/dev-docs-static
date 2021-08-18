# Document.all

**Draft**

This page is not complete.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`Document`](../document) interface's read-only `all` property returns an <span class="page-not-created">`HTMLAllCollection`</span> rooted at the document node. In other words, it returns all of the document's elements, accessible by order (like an array) and by ID (like a regular object).

## Syntax

    var htmlAllCollection = document.all;

### Value

An <span class="page-not-created">`HTMLAllCollection`</span> which contains every element in the document.

## Conversion to boolean

`document.all` is the only [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) object accessible to JavaScript, because it has the [\[\[IsHTMLDDA\]\] internal slot](https://tc39.es/ecma262/#sec-IsHTMLDDA-internal-slot). This was done because of compatibility with older versions of Internet Explorer. More information about this can be found in [this answer from StackOverflow](https://stackoverflow.com/a/62005426).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/obsolete.html#dom-document-all">HTML Living Standard<br />
<span class="small">The definition of 'all' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.<br />
Defined in the obsolete and legacy APIs section.</td></tr></tbody></table>

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

`all`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

24

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

3-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

≤37-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

24

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/all" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/all</a>
