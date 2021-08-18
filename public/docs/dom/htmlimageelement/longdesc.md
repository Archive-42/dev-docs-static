# HTMLImageElement.longDesc

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The _deprecated_ property `longDesc` on the [`HTMLImageElement`](../htmlimageelement) interface specifies the URL of a text or HTML file which contains a long-form description of the image. This can be used to provide optional added details beyond the short description provided in the [`title`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-title) attribute.

## Syntax

    descURL = htmlImageElement.longDesc;
    htmlImageElement.longDesc = descURL;

### Value

A [`DOMString`](../domstring) which may be either an empty string (indicating that no long description is available) or the URL of a file containing a long form description of the image's contents.

For example, if the image is a [PNG](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#png) of a flowchart. The `longDesc` property could be used to provide an explanation of the flow of control represented by the chart, using only text. This can be used by readers both as an explanation, but also as a substitute for visually-impaired users.

## Usage notes

This property is _deprecated_ and should no longer be used. Instead of using `longDesc` to provide a link to a detailed description of an image, encapsulate the image within a link using the [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element.

Consider the following older HTML:

    <img src="taco-tuesday.jpg" longDesc="image-descriptions/taco-tuesday.html">

Here, the `longDesc` is used to indicate that the user should be able to access a detailed description of the image `taco-tuesday.jpg` in the HTML file `image-descriptions/taco-tuesday.html`.

This can be easily converted into modern HTML:

    <a href="image-descriptions/taco-tuesday.html">
      <img src="taco-tuesday.jpg">
    </a>

With that, the image is a link to the HTML file describing the image in more detail.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/objects.html#adef-longdesc-IMG">HTML 4.01 Specification<br />
<span class="small">The definition of 'HTMLImageElement.longDesc' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Provides an actual description of this property; the HTML5 spec only says it's deprecated.</td></tr></tbody></table>

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

`longDesc`

1

12

1

6

≤12.1

3

1

Yes

4

≤12.1

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/longDesc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/longDesc</a>
