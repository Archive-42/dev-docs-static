# HTMLAreaElement.href

The `HTMLAreaElement.href` property is a stringifier that returns a [`USVString`](../usvstring) containing the whole URL, and allows the href to be updated.

## Syntax

    // Getter
    string = area.href;
    // Setter
    area.href = string;

## Examples

    // An <area id="myArea" href="https://developer.mozilla.org/en-US/HTMLAreaElement"> element is in the document
    const area = document.getElementById("myArea");
    area.href; // returns 'https://developer.mozilla.org/en-US/HTMLAreaElement'

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

`href`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- The [`HTMLAreaElement`](../htmlareaelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/href" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/href</a>
