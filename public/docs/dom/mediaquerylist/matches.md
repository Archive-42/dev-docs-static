# MediaQueryList.matches

The `matches` read-only property of the [`MediaQueryList`](../mediaquerylist) interface is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that returns `true` if the [`document`](../document) currently matches the media query list, or `false` if not.

You can be notified when the value of `matches` changes by watching for the <span class="page-not-created">`change`</span> event to be fired at the `MediaQueryList`.

## Syntax

    var matches = <varm>MediaQueryList.matches;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which is `true` if the [`document`](../document) currently matches the media query list; otherwise, it's `false`.

## Examples

This example detects viewport orientation changes by creating a media query using the `orientation` media feature:

    function addMQListener(mq, callback) {
      if (mq.addEventListener) {
        mq.addEventListener("change", callback);
      } else {
        mq.addListener(callback);
      }
    }

    addMQListener(window.matchMedia("(orientation:landscape)"),
      event => {
        if (event.matches) {
          /* now in landscape orientation */
        } else {
          /* now in portrait orientation */
        }
      }
    );

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-mediaquerylist-matches">CSS Object Model (CSSOM) View Module<br />
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

## See also

- [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [Using media queries from code](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries)
- [`window.matchMedia()`](../window/matchmedia)
- [`MediaQueryList`](../mediaquerylist)
- [`MediaQueryListEvent`](../mediaquerylistevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/matches" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/matches</a>
