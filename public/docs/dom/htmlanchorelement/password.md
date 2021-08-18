# HTMLAnchorElement.password

The `HTMLAnchorElement.password` property is a [`USVString`](../usvstring) containing the password specified before the domain name.

If it is set without first setting the `username` property, it silently fails.

## Syntax

    // Getter
    string = anchor.password;
    // Setter
    anchor.password = string;

## Examples

    // An <a id="myAnchor" href="https://anonymous:flabada@developer.mozilla.org/en-US/docs/HTMLAnchorElement"> is in the document
    const anchor = document.getElementByID("myAnchor");
    anchor.password; // returns 'flabada'

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-password">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.password' in that specification.</span></a></td></tr></tbody></table>

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

`password`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/password" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/password</a>
