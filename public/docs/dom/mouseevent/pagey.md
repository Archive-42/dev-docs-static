# MouseEvent.pageY

The `pageY` read-only property of the [`MouseEvent`](../mouseevent) interface returns the Y (vertical) coordinate in pixels of the event relative to the whole document. This property takes into account any vertical scrolling of the page.

## Syntax

    var pos = event.pageY;

Originally, this property was defined as a `long` integer. The CSSOM View Module redefined it as a `double` float. See the Browser compatibility section for details.

## Examples

    var pageY = event.pageY;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-mouseevent-pagey">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'pageY' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Redefined from <code>long</code> to <code>double</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-Touch-pageY">Touch Events<br />
<span class="small">The definition of 'pageY' in that specification.</span></a></td><td><span class="spec-">Unknown</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pageY`

45

12

Yes

9

Yes

Yes

45

45

Yes

Yes

Yes

5.0

`long_to_double`

56

≤79

No

?

?

?

56

56

No

?

?

6.0

## See also

- [`MouseEvent.pageX`](pagex)
- [`UIEvent.pageY`](../uievent/pagey)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/pageY" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/pageY</a>
