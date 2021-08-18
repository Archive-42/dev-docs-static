# Document.URL

The `URL` read-only property of the [`Document`](../document) interface returns the document location as a string.

## Syntax

    const url = document.URL

## Example

### JavaScript

    document.getElementById("url").textContent = document.URL;

### HTML

    <p id="urlText">
      URL:<br/>
      <span id="url">URL goes here</span>
    </p>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-url">DOM<br />
<span class="small">The definition of 'Document.URL' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Defines that the property is a <a href="../usvstring"><code>USVString</code></a> instead of a <a href="../domstring"><code>DOMString</code></a>.</td></tr></tbody></table>

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

`URL`

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

## See also

- The [`document.documentURI`](documenturi) property which returns the same value.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/URL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/URL</a>
