# HTMLImageElement.border

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete [`HTMLImageElement`](../htmlimageelement) property `border` specifies the number of pixels thick the border surrounding the image should be. A value of 0, the default, indicates that no border should be drawn.

You should _not_ use this property! Instead, you should use CSS to style the border. The [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) property or its longhand properties to not only set the thickness of the border but to potentially apply a wide variety of other styling options to it.

The width, specifically, is controlled using the writing-mode aware [`border-block-start-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start-width), [`border-block-end-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-width), [`border-inline-start-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-width), and [`border-inline-end-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-width) properties.

For compatibility (or perhaps other) reasons, you can use the older properties instead (or in addition): [`border-top-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-width), [`border-right-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-width), [`border-bottom-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-width), and [`border-left-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-width).

## Syntax

    htmlImageElement.border = thickness;
    let thickness = htmlImageElement.border;

### Value

A [`DOMString`](../domstring) containing an integer value specifying the thickness of the border that should surround the image, in CSS pixels. A value of `0`, or an empty string, indicates that there should be no border drawn. The default value of `border` is `0`

## Usage notes

Do not use `border`. It is obsolete. Instead, use the CSS [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) property and its longhand properties to establish borders around images.

For example, if you have the following HTML:

    <img src="image.png" border="2">

The following will provide the same appearance using CSS instead of this obsolete property:

    <img src="image.png" style="border: 2px;">

You can further provide additional information to change the color and other features of the border:

    <img src="image.png" style="border: dashed 2px #333388;">

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-border">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.border' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/struct/objects.html#h-13.7.3">HTML 4.01 Specification<br />
<span class="small">The definition of 'HTMLImageElement.border' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`border`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/border" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/border</a>
