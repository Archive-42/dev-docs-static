# @media

The `@media` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](at-rule) can be used to apply part of a style sheet based on the result of one or more [media queries](media_queries/using_media_queries). With it, you specify a media query and a block of CSS to apply to the document if and only if the media query matches the device on which the content is being used.

**Note:** In JavaScript, the rules created using `@media` can be accessed with the [`CSSMediaRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule) CSS object model interface.

## Syntax

The `@media` at-rule may be placed at the top level of your code or nested inside any other [conditional group at-rule](at-rule#conditional_group_rules).

    /* At the top level of your code */
    @media screen and (min-width: 900px) {
      article {
        padding: 1rem 3rem;
      }
    }

    /* Nested within another conditional at-rule */
    @supports (display: flex) {
      @media screen and (min-width: 900px) {
        article {
          display: flex;
        }
      }
    }

For a discussion of media query syntax, please see [Using media queries](media_queries/using_media_queries#syntax).

## Description

### Media types

_Media types_ describe the general category of a device. Except when using the `not` or `only` logical operators, the media type is optional and the `all` type will be implied.

`all`  
Suitable for all devices.

`print`  
Intended for paged material and documents viewed on a screen in print preview mode. (Please see [paged media](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media) for information about formatting issues that are specific to these formats.)

`screen`  
Intended primarily for screens.

`speech`  
Intended for speech synthesizers.

**Deprecated media types:** CSS2.1 and [Media Queries 3](https://drafts.csswg.org/mediaqueries-3/#background) defined several additional media types (`tty`, `tv`, `projection`, `handheld`, `braille`, `embossed`, and `aural`), but they were deprecated in [Media Queries 4](https://dev.w3.org/csswg/mediaqueries/#media-types) and shouldn't be used. The `aural` type has been replaced by `speech`, which is similar.

### Media features

_Media features_ describe specific characteristics of the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent), output device, or environment. Media feature expressions test for their presence or value, and are entirely optional. Each media feature expression must be surrounded by parentheses.

<table><thead><tr class="header"><th>Name</th><th>Summary</th><th>Notes</th></tr></thead><tbody><tr class="odd"><td><a href="@media/any-hover"><code>any-hover</code></a></td><td>Does any available input mechanism allow the user to hover over elements?</td><td>Added in Media Queries Level 4.</td></tr><tr class="even"><td><a href="@media/any-pointer"><code>any-pointer</code></a></td><td>Is any available input mechanism a pointing device, and if so, how accurate is it?</td><td>Added in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="@media/aspect-ratio"><code>aspect-ratio</code></a></td><td>Width-to-height aspect ratio of the viewport</td><td></td></tr><tr class="even"><td><a href="@media/color"><code>color</code></a></td><td>Number of bits per color component of the output device, or zero if the device isn't color</td><td></td></tr><tr class="odd"><td><a href="@media/color-gamut"><code>color-gamut</code></a></td><td>Approximate range of colors that are supported by the user agent and output device</td><td>Added in Media Queries Level 4.</td></tr><tr class="even"><td><a href="@media/color-index"><code>color-index</code></a></td><td>Number of entries in the output device's color lookup table, or zero if the device does not use such a table</td><td></td></tr><tr class="odd"><td><a href="@media/device-aspect-ratio"><code>device-aspect-ratio</code></a> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Width-to-height aspect ratio of the output device</td><td>Deprecated in Media Queries Level 4.</td></tr><tr class="even"><td><a href="@media/device-height"><code>device-height</code></a> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Height of the rendering surface of the output device</td><td>Deprecated in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="@media/device-width"><code>device-width</code></a> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Width of the rendering surface of the output device</td><td>Deprecated in Media Queries Level 4.</td></tr><tr class="even"><td><a href="@media/display-mode"><code>display-mode</code></a></td><td>The display mode of the application, as specified in the web app manifest's <a href="https://developer.mozilla.org/en-US/docs/Web/Manifest#display"><code>display</code></a> member</td><td>Defined in the <a href="https://w3c.github.io/manifest/#the-display-mode-media-feature">Web App Manifest spec</a>.</td></tr><tr class="odd"><td><a href="@media/forced-colors"><code>forced-colors</code></a></td><td>Detect whether user agent restricts color palette</td><td>Added in Media Queries Level 5.</td></tr><tr class="even"><td><a href="@media/grid"><code>grid</code></a></td><td>Does the device use a grid or bitmap screen?</td><td></td></tr><tr class="odd"><td><a href="@media/height"><code>height</code></a></td><td>Height of the viewport</td><td></td></tr><tr class="even"><td><a href="@media/hover"><code>hover</code></a></td><td>Does the primary input mechanism allow the user to hover over elements?</td><td>Added in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="@media/inverted-colors"><code>inverted-colors</code></a></td><td>Is the user agent or underlying OS inverting colors?</td><td>Added in Media Queries Level 5.</td></tr><tr class="even"><td><a href="@media/monochrome"><code>monochrome</code></a></td><td>Bits per pixel in the output device's monochrome frame buffer, or zero if the device isn't monochrome</td><td></td></tr><tr class="odd"><td><a href="@media/orientation"><code>orientation</code></a></td><td>Orientation of the viewport</td><td></td></tr><tr class="even"><td><a href="@media/overflow-block"><code>overflow-block</code></a></td><td>How does the output device handle content that overflows the viewport along the block axis?</td><td>Added in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="@media/overflow-inline"><code>overflow-inline</code></a></td><td>Can content that overflows the viewport along the inline axis be scrolled?</td><td>Added in Media Queries Level 4.</td></tr><tr class="even"><td><a href="@media/pointer"><code>pointer</code></a></td><td>Is the primary input mechanism a pointing device, and if so, how accurate is it?</td><td>Added in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="@media/prefers-color-scheme"><code>prefers-color-scheme</code></a></td><td>Detect if the user prefers a light or dark color scheme</td><td>Added in Media Queries Level 5.</td></tr><tr class="even"><td><a href="@media/prefers-contrast"><code>prefers-contrast</code></a></td><td>Detects if the user has requested the system increase or decrease the amount of contrast between adjacent colors</td><td>Added in Media Queries Level 5.</td></tr><tr class="odd"><td><a href="@media/prefers-reduced-motion"><code>prefers-reduced-motion</code></a></td><td>The user prefers less motion on the page</td><td>Added in Media Queries Level 5.</td></tr><tr class="even"><td><a href="@media/prefers-reduced-transparency"><code>prefers-reduced-transparency</code></a></td><td>The user prefers reduced transparency</td><td>Added in Media Queries Level 5.</td></tr><tr class="odd"><td><a href="@media/resolution"><code>resolution</code></a></td><td>Pixel density of the output device</td><td></td></tr><tr class="even"><td><a href="@media/scan"><code>scan</code></a></td><td>Scanning process of the output device</td><td></td></tr><tr class="odd"><td><a href="@media/scripting"><code>scripting</code></a></td><td>Detects whether scripting (i.e. JavaScript) is available</td><td>Added in Media Queries Level 5.</td></tr><tr class="even"><td><a href="@media/update-frequency"><code>update</code></a></td><td>How frequently the output device can modify the appearance of content</td><td>Added in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="@media/width"><code>width</code></a></td><td>Width of the viewport including width of scrollbar</td><td></td></tr></tbody></table>

## Accessibility concerns

To best accommodate people who adjust a site's text size, use `em`s when you need a [`<length>`](length) for your [media queries](media_queries/using_media_queries).

Both `em` and `px` are valid units, but `em` works better if the user changes the browser text size.

Also consider using Level 4 media queries to improve the user's experience. For example, `prefers-reduced-motion` to [detect if the user has requested that the system minimize the amount of animation](@media/prefers-reduced-motion) or motion it uses.

## Security

Because media queries provide insights into the capabilities—and by extension, the features and design—of the device the user is working with, there is the potential that they could be abused to construct a "fingerprint" which identifies the device, or at least categorizes it to some degree of detail that may be undesirable to users.

Because of this potential, a browser may opt to fudge the returned values in some manner in order to prevent them from being used to precisely identify a computer. A browser might also offer additional measures in this area; for example, if Firefox's "Resist Fingerprinting" setting is enabled, many media queries report default values rather than values representing the actual device state.

## Formal syntax

    @media <media-query-list> {
      <group-rule-body>
    }where
    <media-query-list> = <media-query>#where
    <media-query> = <media-condition> | [ not | only ]? <media-type> [ and <media-condition-without-or> ]?where
    <media-condition> = <media-not> | <media-and> | <media-or> | <media-in-parens>
    <media-type> = <ident>
    <media-condition-without-or> = <media-not> | <media-and> | <media-in-parens>where
    <media-not> = not <media-in-parens>
    <media-and> = <media-in-parens> [ and <media-in-parens> ]+
    <media-or> = <media-in-parens> [ or <media-in-parens> ]+
    <media-in-parens> = ( <media-condition> ) | <media-feature> | <general-enclosed>where
    <media-feature> = ( [ <mf-plain> | <mf-boolean> | <mf-range> ] )
    <general-enclosed> = [ <function-token> <any-value> ) ] | ( <ident> <any-value> )where
    <mf-plain> = <mf-name> : <mf-value>
    <mf-boolean> = <mf-name>
    <mf-range> = <mf-name> [ '<' | '>' ]? '='? <mf-value> | <mf-value> [ '<' | '>' ]? '='? <mf-name> | <mf-value> '<' '='? <mf-name> '<' '='? <mf-value> | <mf-value> '>' '='? <mf-name> '>' '='? <mf-value>where
    <mf-name> = <ident>
    <mf-value> = <number> | <dimension> | <ident> | <ratio>

## Examples

### Testing for print and screen media types

    @media print {
      body { font-size: 10pt; }
    }

    @media screen {
      body { font-size: 13px; }
    }

    @media screen, print {
      body { line-height: 1.2; }
    }

    @media only screen
      and (min-width: 320px)
      and (max-width: 480px)
      and (resolution: 150dpi) {
        body { line-height: 1.4; }
    }

Introduced in Media Queries Level 4 is a new range syntax that allows for less verbose media queries when testing for any feature accepting a range, as shown in the below examples:

    @media (height > 600px) {
        body { line-height: 1.4; }
    }

    @media (400px <= width <= 700px) {
        body { line-height: 1.4; }
    }

For more examples, please see <a href="media_queries/using_media_queries" class="internal">Using media queries</a>.

## Specifications

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Specification</th><th>Comment</th><th>Feedback</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-5/#media-descriptor-table">Media Queries Level 5<br />
<span class="small">The definition of '@media descriptors' in that specification.</span></a></td><td>Reinstates <code>inverted-colors</code> and Custom Media Queries, which were removed from Level 4.<br />
Adds <code>prefers-reduced-motion</code>, <code>prefers-reduced-transparency</code>, <code>prefers-contrast</code>, and <code>prefers-color-scheme</code> media features.</td><td><a href="https://github.com/w3c/csswg-drafts/issues">CSS Working Group drafts GitHub issues</a></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-conditional-3/#at-media">CSS Conditional Rules Module Level 3<br />
<span class="small">The definition of '@media' in that specification.</span></a></td><td>Defines the basic syntax of the <code>@media</code> rule.</td><td><a href="https://github.com/w3c/csswg-drafts/issues">CSS Working Group drafts GitHub issues</a></td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#media">Media Queries Level 4<br />
<span class="small">The definition of '@media' in that specification.</span></a></td><td><p>Adds <code>scripting</code>, <code>pointer</code>, <code>hover</code>, <code>update</code>, <code>overflow-block</code>, and <code>overflow-inline</code> media features.<br />
Deprecates all media types except for <code>screen</code>, <code>print</code>, <code>speech</code>, and <code>all</code>.<br />
Makes the syntax more flexible by adding, among other things, the <code>or</code> keyword.</p></td><td><a href="https://github.com/w3c/csswg-drafts/issues">CSS Working Group drafts GitHub issues</a></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#media0">Media Queries<br />
<span class="small">The definition of '@media' in that specification.</span></a></td><td></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/media.html#at-media-rule">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '@media' in that specification.</span></a></td><td>Initial definition.</td><td></td></tr></tbody></table>

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

`@media`

1

12

1

6

9.2

1.3

1

18

4

10.1

1

1.0

`any-hover`

41

16

64

No

28

9

41

41

64

28

9

5.0

`any-pointer`

41

12

64

No

28

9

41

41

64

28

9

4.0

`aspect-ratio`

3

12

3.5

9

10

5

≤37

18

4

10.1

4.2

1.0

`calc`

66

79

59

No

53

12

66

66

59

47

12

9.0

`color`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`color-gamut`

58

79

No

No

45

10

58

58

No

43

10

7.0

`color-index`

29

79

No

No

16

8

≤37

29

No

16

8

2.0

`device-aspect-ratio`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`device-height`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`device-width`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`display-mode`

45

79

47

Firefox 47 and later support `display-mode` values `fullscreen` and `browser`. Firefox 57 added support for `minimal-ui` and `standalone` values.

No

32

13

45

45

47

Firefox 47 and later support `display-mode` values `fullscreen` and `browser`. Firefox 57 added support for `minimal-ui` and `standalone` values.

32

12.2

5.0

`forced-colors`

89

79

See [bug 970285](https://crbug.com/970285).

79

89

81

No

No

No

No

See [bug 970285](https://crbug.com/970285).

No

See [bug 970285](https://crbug.com/970285).

89

No

No

No

See [bug 970285](https://crbug.com/970285).

`grid`

1

12

2

10

10

3

≤37

18

4

10.1

1

1.0

`height`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`hover`

38

Before Chrome 41, the implementation was buggy and reported `(hover: none)` on non-touch-based computers with a mouse/trackpad. See [bug 441613](https://crbug.com/441613).

12

64

No

28

9

38

Before Chrome 41, the implementation was buggy and reported `(hover: none)` on non-touch-based computers with a mouse/trackpad. See [bug 441613](https://crbug.com/441613).

50

64

28

9

5.0

`inverted-colors`

No

No

No

No

No

9.1

No

No

No

No

10

No

`media_features`

1

12

1

9

9.2

1.3

1

18

4

10.1

3.1

1.0

`media_query_values`

66

79

59

No

53

No

66

66

59

47

No

9.0

`monochrome`

1

79

2

No

10

3

≤37

18

4

10.1

1

1.0

`nested-queries`

26

12

11

No

12.1

6.1

≤37

26

14

12.1

7

1.5

`orientation`

3

12

2

9

10.6

5

≤37

18

4

11

4.2

1.0

`overflow-block`

No

No

66

No

No

No

No

No

66

No

No

No

`overflow-inline`

No

No

66

No

No

No

No

No

66

No

No

No

`pointer`

41

12

64

No

28

9

41

50

64

28

9

5.0

`prefers-color-scheme`

76

79

67

No

62

12.1

76

76

67

54

13

14.2

`prefers-contrast`

No

No

80

No

No

No

No

No

No

No

No

No

`prefers-reduced-data`

85

See [bug 1051189](https://crbug.com/1051189).

85

See [bug 1051189](https://crbug.com/1051189).

No

No

No

No

No

See [bug 1051189](https://crbug.com/1051189).

85

See [bug 1051189](https://crbug.com/1051189).

No

No

No

No

`prefers-reduced-motion`

74

79

63

No

62

10.1

74

74

64

53

10.3

11.0

`prefers-reduced-transparency`

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

`range_syntax`

No

See [bug 1034465](https://crbug.com/1034465).

No

63

No

No

No

No

No

63

No

No

No

`resolution`

29

12

8

3.5

Supports [`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values only.

9

16

10-15

No

See [bug 78087](https://webkit.org/b/78087).

≤37

29

8

4

Supports [`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values only.

16

10.1-14

No

See [bug 78087](https://webkit.org/b/78087).

2.0

`scan`

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

`scripting`

No

See [bug 489957](https://crbug.com/489957).

No

See [bug 489957](https://crbug.com/489957).

No

See [bug 1166581](https://bugzil.la/1166581).

No

No

No

No

See [bug 489957](https://crbug.com/489957).

No

See [bug 489957](https://crbug.com/489957).

No

See [bug 1166581](https://bugzil.la/1166581).

No

No

No

See [bug 489957](https://crbug.com/489957).

`speech_type`

No

No

No

No

9.2

No

No

No

No

10.1

No

No

`update`

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

`width`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`-moz-device-pixel-ratio`

No

No

4

No

No

No

No

No

4

No

No

No

`-webkit-animation`

2-36

No

No

No

15-23

4

2-37

18-36

No

14-24

3.2

1.0-3.0

`-webkit-device-pixel-ratio`

1

12

63

Implemented as an alias for for `-moz-device-pixel-ratio`.

49

Implemented as an alias for for `-moz-device-pixel-ratio`.

45

Implemented as an alias for for `-moz-device-pixel-ratio`.

No

15

3

≤37

18

63

Implemented as an alias for for `-moz-device-pixel-ratio`.

49

Implemented as an alias for for `-moz-device-pixel-ratio`.

45

Implemented as an alias for for `-moz-device-pixel-ratio`.

14

1

1.0

`-webkit-max-device-pixel-ratio`

1

12

63

Implemented as an alias for for `max--moz-device-pixel-ratio`.

49

Implemented as an alias for for `max--moz-device-pixel-ratio`.

45

Implemented as an alias for for `max--moz-device-pixel-ratio`.

No

15

3

≤37

18

63

Implemented as an alias for for `max--moz-device-pixel-ratio`.

49

Implemented as an alias for for `max--moz-device-pixel-ratio`.

45

Implemented as an alias for for `max--moz-device-pixel-ratio`.

14

1

1.0

`-webkit-min-device-pixel-ratio`

1

12

63

Implemented as an alias for for `min--moz-device-pixel-ratio`.

49

Implemented as an alias for for `min--moz-device-pixel-ratio`.

45

Implemented as an alias for for `min--moz-device-pixel-ratio`.

No

15

3

≤37

18

63

Implemented as an alias for for `min--moz-device-pixel-ratio`.

49

Implemented as an alias for for `min--moz-device-pixel-ratio`.

45

Implemented as an alias for for `min--moz-device-pixel-ratio`.

14

1

1.0

`-webkit-transform-2d`

2-36

No

No

No

15-23

4

2-37

18-36

No

14-24

3.2

1.0-3.0

`-webkit-transform-3d`

2-36

12-79

49

46

No

15-23

4

2-37

18-36

49

46

14-24

3.2

1.0-3.0

`-webkit-transition`

2-36

No

No

No

15-23

4

2-37

18-36

No

14-24

3.2

1.0-3.0

## See also

- <a href="media_queries/using_media_queries" class="internal">Using media queries</a>
- In JavaScript, `@media` can be accessed via the CSS object model interface [`CSSMediaRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule).
- [Extended Mozilla media features](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions#media_features)
- [Extended WebKit media features](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions#media_features)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media</a>
