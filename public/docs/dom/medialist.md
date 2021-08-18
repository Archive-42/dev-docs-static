# MediaList

The `MediaList` interface represents the media queries of a stylesheet, e.g. those set using a [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) element's `media` attribute.

<span class="message-body-wrapper"><span class="message-flex-body"><span class="devtools-monospace message-body"><span class="objectBox objectBox-string">**Note**: `MediaList` is a live list; updating the list using properties or methods listed below will immediately update the behavior of the document.</span></span></span></span>

## Properties

[`MediaList.mediaText`](medialist/mediatext)  
A stringifier that returns a [`DOMString`](domstring) representing the `MediaList` as text, and also allows you to set a new `MediaList`.

<span class="page-not-created">`MediaList.length`</span> <span class="badge inline readonly">Read only </span>  
Returns the number of media queries in the `MediaList`.

## Methods

<span class="page-not-created">`MediaList.appendMedium()`</span>  
Adds a media query to the `MediaList`.

<span class="page-not-created">`MediaList.deleteMedium()`</span>  
Removes a media query from the `MediaList`.

<span class="page-not-created">`MediaList.item()`</span>  
A getter that returns a [`CSSOMString`](cssomstring) representing a media query as text, given the media query's index value inside the `MediaList`.

## Examples

The following would log to the console a textual representation of the `MediaList` of the first stylesheet applied to the current document.

    const stylesheets = document.styleSheets;
    let stylesheet = stylesheets[0];
    console.log(stylesheet.media.mediaText);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#the-medialist-interface">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'MediaList' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`MediaList`

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

`appendMedium`

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

`deleteMedium`

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

`item`

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

`length`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaList</a>
