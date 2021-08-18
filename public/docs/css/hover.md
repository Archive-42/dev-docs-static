# :hover

The `:hover` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) matches when the user interacts with an element with a pointing device, but does not necessarily activate it. It is generally triggered when the user hovers over an element with the cursor (mouse pointer).

    /* Selects any <a> element when "hovered" */
    a:hover {
      color: orange;
    }

Styles defined by the `:active` pseudo-class will be overridden by any subsequent link-related pseudo-class ([`:link`](:link), [`:visited`](:visited), or [`:active`](:active)) that has at least equal specificity. To style links appropriately, put the `:hover` rule after the `:link` and `:visited` rules but before the `:active` one, as defined by the _LVHA-order_: `:link` — `:visited` — `:hover` — `:active`.

**Note**: The `:hover` pseudo-class is problematic on touchscreens. Depending on the browser, the `:hover` pseudo-class might never match, match only for a moment after touching an element, or continue to match even after the user has stopped touching and until the user touches another element. Web developers should make sure that content is accessible on devices with limited or non-existent hovering capabilities.

## Syntax

    :hover

## Examples

### Basic example

#### HTML

    <a href="#">Try hovering over this link.</a>

#### CSS

    a {
      background-color: powderblue;
      transition: background-color .5s;
    }

    a:hover {
      background-color: gold;
    }

#### Result

### Image gallery

You can use the `:hover` pseudo-class to build an image gallery with full-size images that show only when the mouse moves over a thumbnail. See <a href="https://developer.mozilla.org/@api/deki/files/6247/=css-gallery.zip" class="internal">this demo</a> for a possible cue.

**Note:** For an analogous effect, but based on the <a href=":checked" class="internal"><code>:checked</code></a> pseudo-class (applied to hidden radioboxes), see <a href="https://developer.mozilla.org/@api/deki/files/6268/=css-checked-gallery.zip" class="internal">this demo</a>, taken from the <a href=":checked" class="internal">:checked</a> reference page.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Comment</th><th>Feedback</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics-other.html#selector-hover">HTML Living Standard<br />
<span class="small">The definition of ':hover' in that specification.</span></a></td><td></td><td><a href="https://github.com/whatwg/html/issues">WHATWG HTML GitHub issues</a></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-4/#the-hover-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':hover' in that specification.</span></a></td><td>Allows <code>:hover</code> to be applied to any pseudo-element.</td><td><a href="https://github.com/w3c/csswg-drafts/issues">CSS Working Group drafts GitHub issues</a></td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-3/#the-user-action-pseudo-classes-hover-act">Selectors Level 3<br />
<span class="small">The definition of ':hover' in that specification.</span></a></td><td></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/selector.html#dynamic-pseudo-classes">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of ':hover' in that specification.</span></a></td><td>Initial definition.</td><td></td></tr></tbody></table>

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

`:hover`

1

12

1

4

4

2

1

18

4

10.1

1

As of Safari for iOS 7.1.2, tapping a [clickable element](https://developer.mozilla.org/docs/Web/Events/click#Safari_Mobile) causes the element to enter the `:hover` state. The element will remain in the `:hover` state until a different element has entered the `:hover` state.

1.0

`a_elements`

1

12

1

4

4

2

37

18

4

10.1

1

1.0

`all_elements`

1

12

In Edge, hovering over an element and then scrolling up or down without moving the pointer will leave the element in the `:hover` state until the pointer is moved. See [bug 5381673](https://developer.microsoft.com/microsoft-edge/platform/issues/5381673/).

1

7

\["In Internet Explorer 8 to Internet Explorer 11, hovering over an element and then scrolling up or down without moving the pointer will leave the element in the `:hover` state until the pointer is moved. See [bug 926665](https://connect.microsoft.com/IE/feedbackdetail/view/926665).", "In Internet Explorer 9 (and possibly earlier), if a [`<table>`](https://developer.mozilla.org/docs/Web/HTML/Element/table) has a parent with a non-`auto` [`width`](https://developer.mozilla.org/docs/Web/CSS/width), [`overflow-x`](https://developer.mozilla.org/docs/Web/CSS/overflow-x)`: auto;`, the [`<table>`](https://developer.mozilla.org/docs/Web/HTML/Element/table) has enough content to horizontally overflow its parent, and there are [`:hover`](https://developer.mozilla.org/docs/Web/CSS/:hover) styles set on elements within the table, then hovering over said elements will cause the [`<table>`](https://developer.mozilla.org/docs/Web/HTML/Element/table)'s height to increase. See [a live demo that triggers the bug](http://jsbin.com/diwiqe). One workaround for the bug is to set `min-height: 0%;` (the `%` unit must be specified, since unitless and `px` don't work) on the `<table>`'s parent element."\]

7

2

37

18

4

10.1

1

1.0

`pseudo_elements`

1

12

28

11

15

2

≤37

18

28

14

1

1.0

## See also

- [Chromium bug \#370155: Don't make `:hover` sticky on tap on sites that set a mobile viewport](https://code.google.com/p/chromium/issues/detail?id=370155)
- [Chromium bug \#306581: Immediately show hover and active states on touch when page isn't scrollable.](https://code.google.com/p/chromium/issues/detail?id=306581)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:hover" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:hover</a>
