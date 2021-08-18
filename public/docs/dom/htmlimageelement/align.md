# HTMLImageElement.align

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The _obsolete_ `align` property of the [`HTMLImageElement`](../htmlimageelement) interface is a string which indicates how to position the image relative to its container. You should instead use the CSS property [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align), which does in fact also work on images despite its name. You can also use the [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float) property to float the image to the left or right margin.

The `align` property reflects the HTML [`align`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-align) content attribute.

## Syntax

    htmlImageElement.align = alignMode;
    alignMode = htmlImageElement.align;

### Value

A [`DOMString`](../domstring) specifying one of the following strings which set the alignment mode for the image.

#### Baseline alignment

These three values specify the alignment of the element relative to the text baseline. These should be replaced by using the CSS [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) property.

`bottom`  
The bottom edge of the image is to be aligned vertically with the current text baseline. **Default value.**

`middle`  
The center of the object should be aligned vertically with the current baseline.

`top`  
The top edge of the object should be aligned vertically with the current baseline.

It may be worth noting that [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) offers several additional options for its value; you may wish to consider these when changing your code to use it.

#### Floating images horizontally

The `left` and `right` properties don't affect the baseline-relative alignment. Instead, they cause the image to "float" to the left or right margin, allowing the following text to flow around the image. You should instead use the CSS [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float) property, specifying as the value either `left` or `right`.

`left`  
Floats the image over to place the left edge flush against the current margin. Any text that follows will flow against the image's right edge.

`right`  
Floats the image to place its right edge flush against the right margin. Subsequent text will flow along the image's left edge.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#attr-img-align">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.align' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/struct/objects.html#adef-align-IMG">HTML 4.01 Specification<br />
<span class="small">The definition of 'HTMLImageElement.align' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`align`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/align" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/align</a>
