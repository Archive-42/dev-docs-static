# Range.cloneContents()

The `Range.cloneContents()` returns a [`DocumentFragment`](../documentfragment) copying the objects of type [`Node`](../node) included in the [`Range`](../range).

Event Listeners added using DOM Events are not copied during cloning. HTML attribute events are duplicated as they are for the DOM Core cloneNode method. HTML id attributes are also cloned, which can lead to an invalid document through cloning.

Partially selected nodes include the parent tags necessary to make the document fragment valid.

## Syntax

    documentFragment = range.cloneContents();

## Example

    range = document.createRange();
    range.selectNode(document.getElementsByTagName("div").item(0));
    documentFragment = range.cloneContents();
    document.body.appendChild(documentFragment);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-clonecontents">DOM<br />
<span class="small">The definition of 'Range.cloneContents()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-cloneContents">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.cloneContents()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`cloneContents`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

## See also

- [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/cloneContents" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/cloneContents</a>
