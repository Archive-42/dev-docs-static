# Element.id

The `id` property of the [`Element`](../element) interface represents the element's identifier, reflecting the `id` global attribute.

If the `id` value is not the empty string, it must be unique in a document.

The `id` is often used with [`getElementById()`](../document/getelementbyid) to retrieve a particular element. Another common case is to use an element's [ID as a selector](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors) when styling the document with [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS).

**Note**: Identifiers are case-sensitive, but you should avoid creating IDs that differ only in the capitalization.

## Syntax

    var idStr = element.id; // Get the id
    element.id = idStr; // Set the id

- `idStr` is the identifier of the element.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-id">DOM<br />
<span class="small">The definition of 'id' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-HTML/">Document Object Model (DOM) Level 2 HTML Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-63534901">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'id' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-63534901">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'id' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`id`

23

1-23

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

12

1

5

≤12.1

1

≤37

1-≤37

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

25

18-25

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

4

≤12.1

1

1.5

1.0-1.5

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

## See also

- The DOM [**id**](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id) global attribute.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/id</a>
