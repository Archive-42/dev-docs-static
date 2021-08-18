MediaList.mediaText
===================

The `mediaText` property of the [`MediaList`](../medialist) interface is a stringifier that returns a [`DOMString`](../domstring) representing the `MediaList` as text, and also allows you to set a new `MediaList`.

Syntax
------

    mediaListInstance.mediaText;
    mediaListInstance.mediaText = string;

### Value

A [`DOMString`](../domstring) representing the media queries of a stylesheet. Each one is separated by a comma, for example `screen and (min-width: 480px), print`.

If you wish to set new media queries on the document, the string value must have the different queries separated by commas, e.g. <span class="message-body-wrapper"><span class="message-flex-body"><span class="devtools-monospace message-body"><span class="objectBox objectBox-string">`screen, print`. Note that the `MediaList` is a live list; updating the list via `mediaText` will immediately update the behavior of the document.</span></span></span></span>

<span class="message-body-wrapper"><span class="message-flex-body"><span class="devtools-monospace message-body"><span class="objectBox objectBox-string">Also note that is you try to set `mediaText` to `null`, it will be treated as an empty string, i.e. the value will be set to `""`.</span></span></span></span>

Examples
--------

The following would log to the console a textual representation of the `MediaList` of the first stylesheet applied to the current document.

    const stylesheets = document.styleSheets;
    let stylesheet = stylesheets[0];
    console.log(stylesheet.media.mediaText);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-medialist-mediatext">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'mediaText' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`mediaText`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaList/mediaText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaList/mediaText</a>
