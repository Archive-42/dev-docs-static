# Location: hash

The `hash` property of the [`Location`](../location) interface returns a [`USVString`](../usvstring) containing a `'#'` followed by the fragment identifier of the URL — the ID on the page that the URL is trying to target.

The fragment is not [percent-decoded](https://developer.mozilla.org/en-US/docs/Glossary/percent-encoding). If the URL does not have a fragment identifier, this property contains an empty string, `""`.

## Syntax

    string = object.hash;
    object.hash = string;

## Examples

    <a id="myAnchor" href="/en-US/docs/Location.href#Examples">Examples</a>
    <script>
      var anchor = document.getElementById("myAnchor");
      console.log(anchor.hash); // Returns '#Examples'
    </script>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-location-hash">HTML Living Standard<br />
<span class="small">The definition of 'hash' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

3

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/hash" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/hash</a>
