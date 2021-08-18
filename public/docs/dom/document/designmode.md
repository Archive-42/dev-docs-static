# Document.designMode

`document.designMode` controls whether the entire document is editable. Valid values are `"on"` and `"off"`. According to the specification, this property is meant to default to `"off"`. Firefox follows this standard. The earlier versions of Chrome and IE default to `"inherit"`. Starting in Chrome 43, the default is `"off"` and `"inherit"` is no longer supported. In IE6-10, the value is capitalized.

## Syntax

    var mode = document.designMode;
    document.designMode = value;

### Value

A string indicating whether `designMode` is (or should be) set to on or off. Valid values are `on` and `off`.

## Example

Make an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)'s document editable:

    iframeNode.contentDocument.designMode = "on";

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#making-entire-documents-editable:-the-designmode-idl-attribute">HTML Living Standard<br />
<span class="small">The definition of 'designMode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`designMode`

1

12

1

4

9

1.2

1

18

4

10.1

1

1.0

## See also

- [Rich-Text Editing in Mozilla](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Editable_content/Rich-Text_Editing_in_Mozilla)
- [`HTMLElement.contentEditable`](../htmlelement/contenteditable)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/designMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/designMode</a>
