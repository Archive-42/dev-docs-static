MediaQueryList.media
====================

The `media` read-only property of the [`MediaQueryList`](../mediaquerylist) interface is a [`DOMString`](../domstring) representing a serialized media query.

Syntax
------

    var media = MediaQueryList.media;

### Value

A [`DOMString`](../domstring) representing a serialized media query.

Examples
--------

This example runs the media query `(max-width: 600px)` and displays the value of the resulting `MediaQueryList`'s `media` property in a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span).

### JavaScript

    let mql = window.matchMedia('(max-width: 600px)');

    document.querySelector(".mq-value").innerText = mql.media;

The JavaScript code passes the media query to match into [`matchMedia()`](../window/matchmedia) to compile it, then sets the `<span>`'s [`innerText`](../htmlelement/innertext) to the value of the result's [`media`](media) property.

### HTML

    <span class="mq-value"></span>

A simple `<span>` to receive the output.

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-mediaquerylist-media">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'media' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`media`

9

12

6

10

12.1

5.1

≤37

18

6

Yes

5

1.0

See also
--------

-   [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
-   [Using media queries from code](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries)
-   [`window.matchMedia()`](../window/matchmedia)
-   [`MediaQueryList`](../mediaquerylist)
-   [`MediaQueryListEvent`](../mediaquerylistevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/media" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/media</a>
