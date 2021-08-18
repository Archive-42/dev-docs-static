# HTMLElement.dir

The `HTMLElement.dir` property gets or sets the text writing directionality of the content of the current element.

The text writing directionality of an element is which direction that text goes (for support of different language systems). Arabic languages and Hebrew are typical languages using the RTL directionality.

An image can have its `dir` property set to "`rtl`" in which case the HTML attributes `title` and `alt` will be formatted and defined as "`rtl`".

When a table has its `dir` set to "`rtl`", the column order is arranged from right to left.

When an element has its dir set to "`auto`", the direction of the element is determined based on its first strong directionality character, or default to the directionality of its parent element.

Browsers might allow users to change the directionality of [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) and [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)s in order to assist with authoring content. Chrome and Safari provide a directionality option in the contextual menu of input fields while Internet Explorer and Edge use the key combinations Ctrl + Left Shift and Ctrl + Right Shift. Firefox uses Ctrl/Cmd + Shift + X but does NOT update the `dir` attribute value.

## Syntax

    var currentWritingDirection = elementNodeReference.dir;
    elementNodeReference.dir = newWritingDirection;

- `currentWritingDirection` is a string variable representing the text writing direction of the current element.
- `newWritingDirection` is a string variable representing the text writing direction value.

Possible values for `dir` are `ltr`, for left-to-right, `rtl`, for right-to-left, and `auto` for specifying that the direction of the element must be determined based on the contents of the element.

## Example

    var parg = document.getElementById("para1");
    parg.dir = "rtl";
    // change the text direction on a paragraph identified as "para1"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-dir">HTML Living Standard<br />
<span class="small">The definition of 'dir' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-HTML/">Document Object Model (DOM) Level 2 HTML Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-52460740">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'dir' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-52460740">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'dir' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`dir`

1

12

1

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

## See also

- [`document.dir`](../document/dir)
- HTML [`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir) global attribute
- CSS [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction) property
- CSS [`:dir`](https://developer.mozilla.org/en-US/docs/Web/CSS/:dir) pseudo-class

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dir" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dir</a>
