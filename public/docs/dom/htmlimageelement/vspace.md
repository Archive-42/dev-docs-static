# HTMLImageElement.vspace

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The _obsolete_ `vspace` property of the [`HTMLImageElement`](../htmlimageelement) interface specifies the number of pixels of empty space to leave empty on the top and bottom of the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element when laying out the page.

## Syntax

    htmlImageElement.vspace = marginHeight;
    marginHeight = htmlImageElement.vspace;

### Value

An integer value specifying the height, in pixels, of the vertical margin to apply to the top and bottom sides of the image.

## Usage notes

The value specified for `vspace` is mapped to the [`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top) and [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom) properties to specify the height of those margins in pixels.

**Important:** This property is obsolete. You should instead use the CSS [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) property and its longhand forms to establish margins around an `<img>`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-vspace">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.vspace' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/struct/objects.html#h-13.7.2">HTML 4.01 Specification<br />
<span class="small">The definition of 'HTMLImageElement.vspace' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The HTML 4.01 specification offers additional details.</td></tr></tbody></table>

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

`vspace`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/vspace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/vspace</a>
