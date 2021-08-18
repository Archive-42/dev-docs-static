# Document.referrer

The `Document.referrer` property returns the [URI](https://www.w3.org/Addressing/#background) of the page that linked to this page.

## Syntax

    var referrer = document.referrer;

### Value

The value is an empty string if the user navigated to the page directly (not through a link, but, for example, by using a bookmark). Because this property returns only a string, it doesn't give you document object model (DOM) access to the referring page.

Inside an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), the `Document.referrer` will initially be set to the same value as the [`href`](../htmlanchorelement/href) of the parent window's [`Window.location`](../window/location).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-referrer-dev">HTML Living Standard<br />
<span class="small">The definition of 'document.referrer' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`referrer`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/referrer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/referrer</a>
