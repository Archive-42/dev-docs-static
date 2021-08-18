# HTMLAreaElement.username

The `HTMLAreaElement.username` property is a [`USVString`](../usvstring) containing the username specified before the domain name.

## Syntax

    // Getter
    string = area.username;
    // Setter
    area.username = string;

## Examples

### Getting the username from an area link

    // An <area id="myArea" href="https://anonymous:flabada@developer.mozilla.org/en-US/docs/HTMLAreaElement"> element is in the document
    const area = document.getElementByID("myArea");
    area.username; // returns 'anonymous'

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

- The [`HTMLAreaElement`](../htmlareaelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/username" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/username</a>
