# MediaQueryListEvent.matches

The `matches` read-only property of the [`MediaQueryListEvent`](../mediaquerylistevent) interface is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that returns `true` if the [`document`](../document) currently matches the media query list, or `false` if not.

## Syntax

    var matches = MediaQueryListEvent.matches;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean); returns `true` if the [`document`](../document) currently matches the media query list, `false` if not.

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
    }

    mql.addListener(screenTest);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-mediaquerylistevent-matches">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'matches' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`matches`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent/matches" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent/matches</a>
