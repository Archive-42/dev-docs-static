MediaQueryListEvent.MediaQueryListEvent()
=========================================

The `MediaQueryListEvent` constructor creates a new `MediaQueryListEvent` instance.

Syntax
------

    var myMqlEvent = new MediaQueryListEvent(init);

### Parameters

init

An init object that defines features of the new object instance. The available properties are:

-   media: A [`DOMString`](../domstring) representing a serialized media query.
-   matches: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) representing the media query status — `true` if it matches, `false` if not.

Examples
--------

    var media = '(max-width: 600px)';
    var matches = true;

    var myMediaQueryListEvent = new MediaQueryListEvent({media, matches});

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-mediaquerylistevent-mediaquerylistevent">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'MediaQueryListEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`MediaQueryListEvent`

39

79

55

No

26

14

39

39

55

26

14

4.0

See also
--------

-   [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
-   [Using media queries from code](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries)
-   [`window.matchMedia()`](../window/matchmedia)
-   [`MediaQueryList`](../mediaquerylist)
-   [`MediaQueryListEvent`](../mediaquerylistevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent/MediaQueryListEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent/MediaQueryListEvent</a>
