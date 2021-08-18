# MediaQueryList.onchange

The `onchange` property of the [`MediaQueryList`](../mediaquerylist) interface is an event handler property representing a function that is invoked when the <span class="page-not-created">`change`</span> event fires, i.e when the status of media query support changes. The event object is a [`MediaQueryListEvent`](../mediaquerylistevent) instance, which is recognized as a `MediaListQuery` instance in older browsers, for backwards compatibility purposes.

## Syntax

    MediaQueryList.onchange = function() { ... };

## Example

    var mql = window.matchMedia('(max-width: 600px)');

    mql.addEventListener( "change", (e) => {
        if (e.matches) {
        /* the viewport is 600 pixels wide or less */
        console.log('This is a narrow screen — less than 600px wide.')
      } else {
        /* the viewport is more than than 600 pixels wide */
        console.log('This is a wide screen — more than 600px wide.')
      }
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-mediaquerylist-onchange">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'onchange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onchange`

45

79

55

No

Yes

14

45

45

55

Yes

14

5.0

## See also

- [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [Using media queries from code](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries)
- [`window.matchMedia()`](../window/matchmedia)
- [`MediaQueryList`](../mediaquerylist)
- [`MediaQueryListEvent`](../mediaquerylistevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/onchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/onchange</a>
