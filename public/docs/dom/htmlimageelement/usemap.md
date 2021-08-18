HTMLImageElement.useMap
=======================

The `useMap` property on the [`HTMLImageElement`](../htmlimageelement) interface reflects the value of the [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) [`usemap`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-usemap) attribute, which is a string providing the name of the client-side image map to apply to the image.

Syntax
------

    htmlImageElement.useMap = imageMapAnchor;
    let imageMapAnchor = htmlImageElement.useMap;

### Value

A [`USVString`](../usvstring) providing the page-local URL (that is, a URL that begins with the hash or pound symbol, "`#`") of the [`<map>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map) element which defines the image map to apply to the image.

You can learn more about client-side image maps in our learning article [Add a hitmap on top of an image](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Add_a_hit_map_on_top_of_an_image).

Usage notes
-----------

The string value of `useMap` must be a valid anchor for a [`<map>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map) element. In other words, this string should be the value of the appropriate `<map>`'s [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map#attr-name) attribute with a pound or hash symbol prepended to it.

Consider a `<map>` that looks like this:

    <map name="mainmenu-map">
      <area shape="circle" coords="25, 25, 75" href="/index.html" alt="Return to home page">
      <area shape="rect" coords="25, 25, 100, 150" href="/index.html" alt="Shop">
    </map>

Given the image map named `mainmenu-map`, the image which uses it should look something like the following:

    <img src="menubox.png" usemap="#mainmenu-map">

For additional examples (including interactive ones), see the articles about the [`<map>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map) and [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) elements, as well as the [guide to using image maps](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Add_a_hit_map_on_top_of_an_image).

Example
-------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-usemap">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.useMap' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`useMap`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/useMap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/useMap</a>
