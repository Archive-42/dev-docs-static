# background-attachment

The `background-attachment` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether a background image's position is fixed within the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport), or scrolls with its containing block.

## Syntax

    /* Keyword values */
    background-attachment: scroll;
    background-attachment: fixed;
    background-attachment: local;

    /* Global values */
    background-attachment: inherit;
    background-attachment: initial;
    background-attachment: unset;

The `background-attachment` property is specified as one of the keyword values from the list below.

### Values

`fixed`  
The background is fixed relative to the viewport. Even if an element has a scrolling mechanism, the background doesn't move with the element. (This is not compatible with [`background-clip: text`](background-clip#text).)

`local`  
The background is fixed relative to the element's contents. If the element has a scrolling mechanism, the background scrolls with the element's contents, and the background painting area and background positioning area are relative to the scrollable area of the element rather than to the border framing them.

`scroll`  
The background is fixed relative to the element itself and does not scroll with its contents. (It is effectively attached to the element's border.)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>scroll</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <attachment>#where
    <attachment> = scroll | fixed | local

## Examples

### Simple example

#### HTML

    <p>
      There were doors all round the hall, but they were all locked; and when
      Alice had been all the way down one side and up the other, trying every
      door, she walked sadly down the middle, wondering how she was ever to
      get out again.
    </p>

#### CSS

    p {
      background-image: url("https://mdn.mozillademos.org/files/12057/starsolid.gif");
      background-attachment: fixed;
    }

#### Result

### Multiple background images

This property supports multiple background images. You can specify a different `<attachment>` for each background, separated by commas. Each image is matched with the corresponding `<attachment>` type, from first specified to last.

#### HTML

    <p>
      There were doors all round the hall, but they were all locked; and when
      Alice had been all the way down one side and up the other, trying every
      door, she walked sadly down the middle, wondering how she was ever to
      get out again.

      Suddenly she came upon a little three-legged table, all made of solid
      glass; there was nothing on it except a tiny golden key, and Alice's
      first thought was that it might belong to one of the doors of the hall;
      but, alas! either the locks were too large, or the key was too small,
      but at any rate it would not open any of them. However, on the second
      time round, she came upon a low curtain she had not noticed before, and
      behind it was a little door about fifteen inches high: she tried the
      little golden key in the lock, and to her great delight it fitted!
    </p>

#### CSS

    p {
      background-image: url("https://mdn.mozillademos.org/files/12057/starsolid.gif"),
          url("https://mdn.mozillademos.org/files/12059/startransparent.gif");
      background-attachment: fixed, scroll;
      background-repeat: no-repeat, repeat-y;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-background-attachment">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'background-attachment' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The shorthand property has been extended to support multiple backgrounds and the <code>local</code> value.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/colors.html#propdef-background-attachment">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'background-attachment' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#background-attachment">CSS Level 1<br />
<span class="small">The definition of 'background-attachment' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant change.</td></tr></tbody></table>

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

`background-attachment`

1

12

1

4

3.5

1

≤37

18

4

10.1

3.2

1.0

`fixed`

1

12

25

9

10.5

No

37

18

25

14

4.2

1.0

`local`

1

12

25

9

10.5

No

37

18

25

14

4.2

1.0

`multiple_backgrounds`

1

12

3.6

9

10.5

1.3

≤37

18

4

11

3.2

1.0

## See also

- [Using multiple backgrounds](css_backgrounds_and_borders/using_multiple_backgrounds)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-attachment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/background-attachment</a>
