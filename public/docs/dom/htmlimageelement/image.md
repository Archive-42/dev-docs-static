Image()
=======

The `Image()` constructor creates a new [`HTMLImageElement`](../htmlimageelement) instance. It is functionally equivalent to [`document.createElement('img')`](../document/createelement).

**Disambiguation:** [`image()`, the CSS function notation](https://developer.mozilla.org/en-US/docs/Web/CSS/image()).

Syntax
------

    var htmlImageElement = new Image(width, height);

### Parameters

`width`  
The width of the image (i.e., the value for the [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-width) attribute).

`height`  
The height of the image (i.e., the value for the [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-height) attribute).

Usage note
----------

The entire bitmap is loaded regardless of the sizes specified in the constructor. The size specified in the constructor is reflected through the properties [`HTMLImageElement.width`](width) and [`HTMLImageElement.height`](height) of the resulting instance. The intrinsic width and height of the image in CSS pixels are reflected through the properties [`HTMLImageElement.naturalWidth`](naturalwidth) and [`HTMLImageElement.naturalHeight`](naturalheight). If no size is specified in the constructor both pairs of properties have the same values.

<span style="line-height: 1.572;">Examples</span>
-------------------------------------------------

    var myImage = new Image(100, 200);
    myImage.src = 'picture.jpg';
    document.body.appendChild(myImage);

This would be the equivalent of defining the following HTML tag inside the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body):

    <img width="100" height="200" src="picture.jpg">

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#dom-image">HTML Living Standard<br />
<span class="small">The definition of 'Image()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`Image`

1

12

1

5.5

8

10.1

1

18

4

?

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/Image" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/Image</a>
