# HTMLAnchorElement.toString()

The `HTMLAnchorElement.toString()` stringifier method returns a [`USVString`](../usvstring) containing the whole URL. It is a read-only version of [`HTMLAnchorElement.href`](href).

## Syntax

    anchor.toString();

## Examples

### Calling toString on an anchor element

    // An <a id="myAnchor" href="/en-US/docs/HTMLAnchorElement"> element is in the document
    const anchor = document.getElementById("myAnchor");
    anchor.toString(); // returns 'https://developer.mozilla.org/en-US/docs/HTMLAnchorElement'

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-href">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.href' in that specification.</span></a></td></tr></tbody></table>

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

`toString`

52

≤18

22

No

Yes

Yes

52

52

22

Yes

Yes

6.0

## See also

- The [`HTMLAnchorElement`](../htmlanchorelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/toString</a>
