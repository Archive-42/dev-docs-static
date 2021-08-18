# CaretPosition

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CaretPosition` interface represents the caret position, an indicator for the text insertion point. You can get a `CaretPosition` using the [`Document.caretPositionFromPoint()`](document/caretpositionfrompoint) method.

## Properties

_This interface doesn't inherit any properties._

<span class="page-not-created">`CaretPosition.offsetNode`</span> <span class="badge inline readonly">Read only </span>  
Returns a [`Node`](node) containing the found node at the caret's position.

<span class="page-not-created">`CaretPosition.offset`</span> <span class="badge inline readonly">Read only </span>  
Returns a `long` representing the character offset in the caret position node.

## Methods

<span class="page-not-created">`CaretPosition.getClientRect`</span>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#caret-position">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'CaretPosition' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`CaretPosition`

No

No

20

No

No

No

No

No

20

No

No

No

`getClientRect`

No

No

23

No

No

No

No

No

23

No

No

No

`offset`

No

No

20

No

No

No

No

No

20

No

No

No

`offsetNode`

No

No

20

No

No

No

No

No

20

No

No

No

## See also

- [`Document.caretPositionFromPoint()`](document/caretpositionfrompoint)
- [`Range`](range)
- [`Node`](node)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CaretPosition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CaretPosition</a>
