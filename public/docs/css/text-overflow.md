# text-overflow

The `text-overflow` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how hidden overflow content is signaled to users. It can be clipped, display an ellipsis ('`…`'), or display a custom string.

The `text-overflow` property doesn't force an overflow to occur. To make text overflow its container you have to set other CSS properties: [`overflow`](overflow) and [`white-space`](white-space). For example:

    overflow: hidden;
    white-space: nowrap;

The `text-overflow` property only affects content that is overflowing a block container element in its _inline_ progression direction (not text overflowing at the bottom of a box, for example).

## Syntax

The `text-overflow` property may be specified using one or two values. If one value is given, it specifies overflow behavior for the end of the line (the right end for left-to-right text, the left end for right-to-left text). If two values are given, the first specifies overflow behavior for the left end of the line, and the second specifies it for the right end of the line.

Each value is specified as one of:

- one of the keyword values: `clip`, `ellipsis`, `fade`
- the function `fade()`, which is passed a [`<length>`](length) or a [`<percentage>`](percentage) to control the fade distance
- a `<string>`.

### Values

`clip`  
The default for this property. This keyword value will truncate the text at the limit of the [content area](css_box_model/introduction_to_the_css_box_model), therefore the truncation can happen in the middle of a character. To clip at the transition between characters you can specify `text-overflow` as an empty string, if that is supported in your target browsers: `text-overflow: '';`.

`ellipsis`  
This keyword value will display an ellipsis (`'…'`, `U+2026 Horizontal Ellipsis`) to represent clipped text. The ellipsis is displayed inside the [content area](css_box_model/introduction_to_the_css_box_model), decreasing the amount of text displayed. If there is not enough space to display the ellipsis, it is clipped.

`<string>` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The [`<string>`](string) to be used to represent clipped text. The string is displayed inside the [content area](css_box_model/introduction_to_the_css_box_model), shortening the size of the displayed text. If there is not enough space to display the string itself, it is clipped.

`fade` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
This keyword clips the overflowing inline content and applies a fade-out effect near the edge of the line box with complete transparency at the edge.

`fade( <length> | <percentage> )` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
This function clips the overflowing inline content and applies a fade-out effect near the edge of the line box with complete transparency at the edge.

The argument determines the distance over which the fade effect is applied. The [`<percentage>`](percentage) is resolved against the width of the line box. Values lower than `0` are clipped to `0`. Values greater than the width of the line box are clipped to the width of the line box.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>clip</code></td></tr><tr class="even"><td>Applies to</td><td>block container elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ clip | ellipsis | <string> ]{1,2}

## Examples

### CSS

    p {
      width: 200px;
      border: 1px solid;
      padding: 2px 5px;

      /* BOTH of the following are required for text-overflow */
      white-space: nowrap;
      overflow: hidden;
    }

    .overflow-visible {
      white-space: initial;
    }

    .overflow-clip {
      text-overflow: clip;
    }

    .overflow-ellipsis {
      text-overflow: ellipsis;
    }

    .overflow-string {
      /* Not supported in most browsers,
         see the 'Browser compatibility' section below */
      text-overflow: " [..]";
    }

### HTML

    <p class="overflow-visible">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
    <p class="overflow-clip">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
    <p class="overflow-ellipsis">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
    <p class="overflow-string">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>

### Result

**Note:** Live results in the following table may be shown incorrectly due to a limitation of the MDN Editor which removes the all contents of style attributes which have `text-overflow` properties with string value.

CSS value

`direction: ltr`

`direction: rtl`

Expected Result

Live result

Expected Result

Live result

_visible overflow_

1234567890

1234567890

0987654321

1234567890

`text-overflow: clip`

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADoAAAAaCAMAAADRyb8sAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAGPUExURf///5jP7J7P7E41NGs4NfHTov/79DMzM///+///9+bq70I0MzE2UJBKOP/+9PX9//z//2I3Nfj//+79/8bl9Vk2NOn+/8/y/i5MjePTve/JlvDTrJVKOObm5vz18Xo6NpvP8M6qhZfL7J2sp/Ht6P/52+ro5tu/m//xzTdqmvTcuOG9i5TI56TU8eTh5PXcszFHcjl8tTE3W82dZP/93is+hi46bsPDxaHV9sakjNPQ1MGei9zUz9XTxn+qvq/Z9eDu6muRs7aCV+fz+lR8p+bq8nes1reYi6p6S/7u0UyTy2SfzFV6m1mZzP/95H6rzDdRXPv7/5NoOtq0f6C1xEuDrMzd4WVqjqPP7cDAu7rd8Yaqueb+/87q+Wal0eTy821GNt32/jA4Za7V8byQWLuCP3M5NfLlzODKsTBYmYWw1s3i7sGXbI+AYNWvht/v+s+dW7fFyfbz92Z0lbB6PixOmdDd5UNGXNjJrf/96IWco9Ckbm6WnFBSXNmqb1tENenx1p2Wg/7uzYI7NkZQUUzy1BAAAAFhSURBVDjL7VPXUgJBEBy484bjUJEkiAISBERBMuacc84555xz+HB3Dyy9syjffGJeerd3e6anZhcgF/8T7kIRbMFOEVXuYJoATi27yUl2qloGnRTLEbFDD9DLIkbmxKMLrCYwTg5wiRJeQSqtdxUpCfpwctmLVQCh6f3trbCWUFbEGQLRxGkyeUwWAWyVueBLFTRFUAcxdjBNbe4Sy7fvD2LSk0v9GSU9bL+81YJ8RWYVEA3CziGtDk/xFyOVRonfhAEgD0eYbNIQhnW0/gHiHsAbk4oZU9T3+ZWFNZuIVOPKIq1kzAuZFjbWVuEe716F6/U0U6IpJlIn/OrVQcEq+PWq0e+bRx+Pzxgx/JQ6ZMKGRntTXTv4inB+dqwP+J6BKctK3ESneCMM64DvnlCLhofs/haJ1MPSsSlJThpdAHS+NWIxSjUD30aJRdqREf94XFyFWishbF8EV5b7ernIEp8LpSv1wkFuHQAAAABJRU5ErkJggg==" alt="t-o_clip.png" class="default internal" width="58" height="26" />

1234567890

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADkAAAAYCAMAAAB3NqUkAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAGzUExURf///8/y/v/+9C1Nk/X+/9Ty/vHTojMzMzE2UPH+////++Th4vbv6uz+//j////wzebm5pzP7DI0Q///91R8pf/32bTc9P/+8EI0M+X+//nZpTE3W+7r7ebq8tf2/uvx92s4NfXcu1k2NP/59fL5/041NPv7/8qvjbV6PmI3NcjIxaRpOy47duP5/qp6W/P3+U2WzjVrpzA4ZSw8fvfcs5NKON74/t+3gy46bq6rkvz//9PQ2P7y3/3p0Zp5YP7z56fAztPQ1JWAYI+Klr6jffXXovPv6syqhdWqd/rpyJDF53es1oeCj4221jJHb1mZzGGKrevz+n6r0X1gZ7HF026m0b3P3JNoOsDG09u/m6TU8aeBVubl2pZVOUuDrLGJV6jF1+zOqPT26z2EuO3TrvnhvvTTnaOWg/rp1sDAuzp8si5MjYaqueTy8+O/jjdqmv/938ypfrCDam6ds5dfOuvu6uPq6oWlvs3i7mOf0TBYmbGJYoteOX6rzMqXWsOpfmVqh/HSne/p2l57oaHA119mXTlpjVBSXI+AYCxOmZ+ppPrv51xRRSlAk1NcUsCQWaNgO3avYvMAAAF2SURBVDjL7ZLVV0JBEMaH0LmAtCilIIiISkvZ3d3d3d3drX+ye9fLOeDh1QfP4XvY2flmf2fnzl2ApP5caZKsX4aJ87tptEbramNJ7LHMU8QiJ/ALEZHhsY7GIRAR30WMHgBxI4npUoCyCq4eVaHqzp0HwB/fLSgYErLOJ56QqOmdmpn0ZYMcJ9aHsQWgvLbGkBJLYgYN/IDS6qa7YiYiEP7UFlQ8EEtksGXuZFM9E0/e462TkHtcU5kBj/6dkkuL2lkZPbOBI2xI/UU+RLReIah3Dg/seAwQCuv0zxSYt6BXRLvAFVkCMhyEUPTL8wUi9Zfv5Ym5CtJ8GpVkzbGt6iAB6ZfCdQzJd308vmE6vQs0NkLOaTel4jw2rWey47o9vznz66C5bWDfjv2s83pZdATQ1NE3NkrGJ3fg2vKgB6Cyuk5VVRpDbpPfSMYrN5MJddGrLhDJcHMsxGgnLSKrVm5jiHsxilwaGxSmuJckNnKFpP6FvgFXcjK6nyJmWAAAAABJRU5ErkJggg==" alt="t-o_clip_rtl.png" class="default internal" width="57" height="24" />

1234567890

`text-overflow: ''`

12345

1234567890

54321

1234567890

`text-overflow: ellipsis`

1234…

1234567890

…4321

1234567890

`text-overflow: '.'`

1234.

1234567890

.4321

1234567890

`text-overflow: clip clip`

123456

1234567890

654321

1234567890

`text-overflow: clip ellipsis`

1234…

1234567890

6543…

1234567890

`text-overflow: clip '.'`

1234.

1234567890

6543.

1234567890

`text-overflow: ellipsis clip`

…3456

1234567890

…4321

1234567890

`text-overflow: ellipsis ellipsis`

…34…

1234567890

…43…

1234567890

`text-overflow: ellipsis '.'`

…34.

1234567890

…43.

1234567890

`text-overflow: ',' clip`

,3456

1234567890

,4321

1234567890

`text-overflow: ',' ellipsis`

,34…

1234567890

,43…

1234567890

`text-overflow: ',' '.'`

,34.

1234567890

,43.

1234567890

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overflow-4/#text-overflow">CSS Overflow Module Level 4</a></td><td></td><td>Added the values <code>&lt;string&gt;</code> and <code>fade</code> and the <code>fade()</code> function</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-overflow-3/#text-overflow">CSS Overflow Module Level 3<br />
<span class="small">The definition of 'text-overflow' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

A previous version of this interface reached the _Candidate Recommendation_ status. As some not-listed-at-risk features needed to be removed, the spec was demoted to the _Working Draft_ level, explaining why browsers implemented this property unprefixed, though not at the CR state.

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

`text-overflow`

1

12

7

Until Firefox 10, handling of `text-overflow` on blocks with inline overflow on both horizontal sides was incorrect. Before Firefox 10, if only one value was specified (such as `text-overflow: ellipsis;`), text was ellipsed on both sides of the block, instead of only the end edge based on the block's text direction.

6

8

11

9-15

1.3

≤37

18

7

Until Firefox 10, handling of `text-overflow` on blocks with inline overflow on both horizontal sides was incorrect. Before Firefox 10, if only one value was specified (such as `text-overflow: ellipsis;`), text was ellipsed on both sides of the block, instead of only the end edge based on the block's text direction.

11

10.1-14

1

1.0

`fade_function`

No

No

No

No

No

No

No

No

No

No

No

No

`fade_value`

No

No

No

No

No

No

No

No

No

No

No

No

`string`

No

No

9

No

No

No

No

No

9

No

No

No

`two_value_syntax`

No

No

9

No

No

No

No

No

9

No

No

No

## See also

- Related CSS properties: [`overflow`](overflow), [`white-space`](white-space)
- CSS properties that control line breaks in words: [`overflow-wrap`](overflow-wrap), [`word-break`](word-break)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow</a>
