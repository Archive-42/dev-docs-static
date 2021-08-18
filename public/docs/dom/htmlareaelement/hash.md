# HTMLAreaElement.hash

The `HTMLAreaElement.hash` property returns a [`USVString`](../usvstring) containing a `'#'` followed by the fragment identifier of the URL.

The fragment is not [percent-decoded](https://developer.mozilla.org/en-US/docs/Glossary/percent-encoding). If the URL does not have a fragment identifier, this property contains an empty string, `""`.

## Syntax

    // Getter
    string = area.hash;
    // Setter
    area.hash = string;

## Examples

### Getting the hash from an area link

Given this HTML

    <map name="infographic">
      <area id="mdn-circle" shape="circle" coords="130,136,60"
      href="https://developer.mozilla.org/#ExampleSection" alt="MDN" />
    </map>

    <img usemap="#infographic" src="/media/examples/mdn-info.png" alt="MDN infographic" />

you can get the hash of the area link like this:

    const area = document.getElementById("mdn-circle");
    area.hash; // returns '#ExampleSection'

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

- The [`HTMLAreaElement`](../htmlareaelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/hash" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/hash</a>
