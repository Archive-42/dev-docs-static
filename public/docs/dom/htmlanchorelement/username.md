# HTMLAnchorElement.username

The `HTMLAnchorElement.username` property is a [`USVString`](../usvstring) containing the username specified before the domain name.

## Syntax

    // Getter
    string = anchor.username;
    // Setter
    anchor.username = string;

## Examples

### Getting the username from an anchor link

    // An <a id="myAnchor" href="https://anonymous:flabada@developer.mozilla.org/en-US/docs/HTMLAnchorElement"> element is in the document
    const anchor = document.getElementByID("myAnchor");
    anchor.username; // returns 'anonymous'

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-username">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.username' in that specification.</span></a></td></tr></tbody></table>

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

`username`

32

79

26

No

19

10

4.4.3

32

26

19

10

2.0

## See also

- The [`HTMLAnchorElement`](../htmlanchorelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/username" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/username</a>
