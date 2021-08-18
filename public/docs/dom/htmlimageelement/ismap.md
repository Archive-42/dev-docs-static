HTMLImageElement.isMap
======================

The [`HTMLImageElement`](../htmlimageelement) property `isMap` is a Boolean value which indicates that the image is to be used by a server-side image map. This may only be used on images located within an [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element.

**Note:** For accessibility reasons, you should generally avoid using server-side image maps, as they require the use of a mouse. Use a [client-side image map](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Add_a_hit_map_on_top_of_an_image) instead.

Syntax
------

    htmlImageElement.isMap = true|false;
    let isMap = htmlImageElement.isMap;

### Value

A Boolean value which is `true` if the image is being used for a server-side image map; otherwise, the value is `false`.

Usage notes
-----------

When an image marked as being part of a server-side image map is clicked, the browser constructs the string "?x,y", where x and y indicate the coordinates at which the mouse was clicked as offsets from the top-left corner of the image, specified in CSS pixels.

The browser then fetches that URL from the server and displays or downloads it depending on the value of the [`download`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-download) attribute.

Unlike server-side image maps, client-side image maps don't cause the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element to adopt interactive content mode.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-ismap">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.isMap' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`isMap`

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

The compatibility table on this page is generated from structured data. If you'd like to contribute to the data, please check out <https://github.com/mdn/browser-compat-data> and send us a pull request.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/isMap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/isMap</a>
