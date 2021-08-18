# Element.prefix

The `Element.prefix` read-only property returns the namespace prefix of the specified element, or `null` if no prefix is specified.

## Syntax

    string = element.prefix

## Examples

The following logs "x" to the console.

    <x:div onclick="console.log(this.prefix)"/>

## Notes

This will only work when a namespace-aware parser is used, i.e. when a document is served with an XML MIME type. This will not work for HTML documents.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-prefix">DOM<br />
<span class="small">The definition of 'Element: prefix' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`prefix`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- [`Element.namespaceURI`](namespaceuri)
- [`Element.localName`](localname)
- [`Attr.prefix`](../attr/prefix)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/prefix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/prefix</a>
