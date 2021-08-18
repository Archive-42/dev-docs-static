# Range()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Range()` constructor returns a newly created [`Range`](../range) object whose start and end is the global [`Document`](../document) object.

## Syntax

    range = new Range()

## Example

In this example we create a new range with the `Range()` constructor, and set its beginning and end positions using the [`Range.setStartBefore()`](setstartbefore) and [`Range.setEndAfter()`](setendafter) methods. We then select the range using [`window.getSelection()`](../window/getselection) and [`Selection.addRange()`](../selection/addrange).

### HTML

    <p>First paragraph.</p>
    <p>Second paragraph.</p>
    <p>Third paragraph.</p>
    <p>Fourth paragraph.</p>

### JavaScript

    const paragraphs = document.querySelectorAll('p');

    // Create new range
    const range = new Range();

    // Start range at second paragraph
    range.setStartBefore(paragraphs[1]);

    // End range at third paragraph
    range.setEndAfter(paragraphs[2]);

    // Get window selection
    const selection = window.getSelection();

    // Add range to window selection
    selection.addRange(range);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-range">DOM<br />
<span class="small">The definition of 'Range.Range()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Range`

29

15

24

No

16

6.1

≤37

29

24

16

8

2.0

## See also

- [The DOM interfaces index](../document_object_model)
- [`Document.createRange()`](../document/createrange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/Range" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/Range</a>
