Window.matchMedia()
===================

The [`Window`](../window) interface's `matchMedia()` method returns a new [`MediaQueryList`](../mediaquerylist) object that can then be used to determine if the [`document`](../document) matches the [media query](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) string, as well as to monitor the document to detect when it matches (or stops matching) that media query.

Syntax
------

    mqList = window.matchMedia(mediaQueryString)

### Parameters

`mediaQueryString`  
A string specifying the media query to parse into a [`MediaQueryList`](../mediaquerylist).

### Return value

A new [`MediaQueryList`](../mediaquerylist) object for the media query. Use this object's properties and events to detect matches and to monitor for changes to those matches over time.

Usage notes
-----------

You can use the returned media query to perform both instantanteous and event-driven checks to see if the document matches the media query.

To perform a one-time, instantaneous check to see if the document matches the media query, look at the value of the [`matches`](../mediaquerylist/matches) property, which will be `true` if the document meets the media query's requirements.

If you need to be kept aware of whether or not the document matches the media query at all times, you can instead watch for the <span class="page-not-created">`change`</span> event to be delivered to the object. There's [a good example of this](devicepixelratio#example) in the article on [`Window.devicePixelRatio`](devicepixelratio).

Examples
--------

This example runs the media query `(max-width: 600px)` and displays the value of the resulting `MediaQueryList`'s `matches` property in a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span); as a result, the output will say "true" if the viewport is less than or equal to 600 pixels wide, and will say "false" if the window is wider than that.

### JavaScript

    let mql = window.matchMedia('(max-width: 600px)');

    document.querySelector(".mq-value").innerText = mql.matches;

The JavaScript code passes the media query to match into [`matchMedia()`](matchmedia) to compile it, then sets the `<span>`'s [`innerText`](../htmlelement/innertext) to the value of the results' [`matches`](../mediaquerylist/matches) property, so that it indicates whether or not the document matches the media query at the moment the page was loaded.

### HTML

    <span class="mq-value"></span>

A simple `<span>` to receive the output.

### Result

See [Testing media queries programmatically](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries) for additional code examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-matchmedia">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Window.matchMedia()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`matchMedia`

9

12

6

10

12.1

5.1

≤37

18

6

12.1

5

1.0

See also
--------

-   [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
-   [Using media queries from code](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries)
-   [`MediaQueryList`](../mediaquerylist)
-   [`MediaQueryList`](../mediaquerylist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia</a>
