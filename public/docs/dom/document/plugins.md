# Document.plugins

The `plugins` read-only property of the [`Document`](../document) interface returns an [`HTMLCollection`](../htmlcollection) object containing one or more [`HTMLEmbedElement`](../htmlembedelement)s representing the [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed) elements in the current document.

For a list of installed plugins, use [NavigatorPlugins.plugins](../navigatorplugins/plugins) instead.

## Syntax

    embedArrayObj = document.plugins

### Value

An [`HTMLCollection`](../htmlcollection), or `null` if there are no embeds in the document.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-plugins">HTML Living Standard<br />
<span class="small">The definition of 'Document.plugins' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`plugins`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

10.1

3-10.1

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

10.3

1-10.3

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

## See also

- [MSDN documentation](<https://docs.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537477(v=vs.85)>)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/plugins" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/plugins</a>
