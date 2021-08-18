# Document.writeln()

Writes a string of text followed by a newline character to a document.

## Syntax

    document.writeln(line);

### Parameters

- `line` is string containing a line of text.

## Example

    document.writeln("<p>enter password:</p>");

## Notes

**document.writeln** is the same as [`document.write`](write) but adds a newline.

**Note:** **document.writeln** (like **document.write**) does not work in XHTML documents (you'll get a "Operation is not supported" (`NS_ERROR_DOM_NOT_SUPPORTED_ERR`) error on the error console). This is the case if opening a local file with a .xhtml file extension or for any document served with an application/xhtml+xml MIME type. More information is available in the [W3C XHTML FAQ](https://www.w3.org/MarkUp/2004/xhtml-faq#docwrite).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-writeln">HTML Living Standard<br />
<span class="small">The definition of 'document.writeln()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-35318390">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'document.writeln()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

`writeln`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/writeln" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/writeln</a>
