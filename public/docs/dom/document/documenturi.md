# Document.documentURI

The `documentURI` read-only property of the [`Document`](../document) interface returns the document location as a string.

## Syntax

    const uri = document.documentURI

## Example

### JavaScript

    document.getElementById("url").textContent = document.documentURI;

### HTML

    <p id="urlText">
      URL:<br/>
      <span id="url">URL goes here</span>
    </p>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-documenturi">DOM<br />
<span class="small">The definition of 'documentURI' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`documentURI`

1

17

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`readonly`

43

≤79

Yes

No

30

No

43

43

Yes

30

No

4.0

## See also

- The [`document.URL`](url) property which returns the same value.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/documentURI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/documentURI</a>
