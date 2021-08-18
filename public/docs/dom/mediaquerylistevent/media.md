# MediaQueryListEvent.media

The `media` read-only property of the [`MediaQueryListEvent`](../mediaquerylistevent) interface is a [`DOMString`](../domstring) representing a serialized media query.

## Syntax

    var media = MediaQueryListEvent.media;

### Value

A [`DOMString`](../domstring) representing a serialized media query.

## Examples

    var mql = window.matchMedia('(max-width: 600px)');

    function screenTest(e) {
      if (e.matches) {
        /* the viewport is 600 pixels wide or less */
        para.textContent = 'This is a narrow screen — less than 600px wide.';
        document.body.style.backgroundColor = 'red';
      } else {
        /* the viewport is more than than 600 pixels wide */
        para.textContent = 'This is a wide screen — more than 600px wide.';
        document.body.style.backgroundColor = 'blue';
      }

      console.log(e.media);
    }

    mql.addListener(screenTest);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-mediaquerylistevent-media">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'media' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`media`

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

## See also

- [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [Using media queries from code](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries)
- [`window.matchMedia()`](../window/matchmedia)
- [`MediaQueryList`](../mediaquerylist)
- [`MediaQueryListEvent`](../mediaquerylistevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent/media" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent/media</a>
