# HTMLAnchorElement.hash

The `HTMLAnchorElement.hash` property returns a [`USVString`](../usvstring) containing a `'#'` followed by the fragment identifier of the URL.

The fragment is not [percent-decoded](https://developer.mozilla.org/en-US/docs/Glossary/percent-encoding). If the URL does not have a fragment identifier, this property contains an empty string, `""`.

## Syntax

    // Getter
    string = anchor.hash;
    // Setter
    anchor.hash = string;

## Examples

### Getting the hash from an anchor link

Given this HTML

    <a id="myAnchor" href="/en-US/docs/HTMLAnchorElement#Examples">Examples</a>

you can get the hash of the anchor like this:

    const anchor = document.getElementById("myAnchor");
    anchor.hash; // returns '#Examples'

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-hash">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.hash' in that specification.</span></a></td></tr></tbody></table>

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

`hash`

1

12

1

From Firefox 29 to Firefox 40, the returned value was incorrectly percent-decoded.

5

15

1

1

18

4

From Firefox 29 to Firefox 40, the returned value was incorrectly percent-decoded.

14

1

1.0

## See also

- The [`HTMLAnchorElement`](../htmlanchorelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/hash" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/hash</a>
