# HTMLElement.offsetTop

The `HTMLElement.offsetTop` read-only property returns the distance of the outer border of the current element relative to the inner border of the top of the [`offsetParent`](offsetparent) node.

## Syntax

    topPos = element.offsetTop;

### Parameters

- `topPos` is the number of pixels from the top of the _closest relatively positioned_ parent element.

## Example

    var d = document.getElementById("div1");
    var topPos = d.offsetTop;

    if (topPos > 10) {
      // object is offset more
      // than 10 pixels from its parent
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-htmlelement-offsettop">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'offsetTop' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

## Browser compatibility

BCD tables only load in the browser

In compliance with the specification, this property will return `null` on Webkit if the element is hidden (the `style.display` of this element or any ancestor is `"none"`) or if the `style.position` of the element itself is set to `"fixed"`.

This property will return `null` on Internet Explorer (9) if the `style.position` of the element itself is set to `"fixed"`. (Having `display:none` does not affect this browser.)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetTop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetTop</a>
