# cursor

The `cursor` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the type of mouse cursor, if any, to show when the mouse pointer is over an element.

## Syntax

    /* Keyword value */
    cursor: pointer;
    cursor: auto;

    /* URL, with a keyword fallback */
    cursor: url(hand.cur), pointer;

    /* URL and coordinates, with a keyword fallback */
    cursor: url(cursor1.png) 4 12, auto;
    cursor: url(cursor2.png) 2 2, pointer;

    /* Global values */
    cursor: inherit;
    cursor: initial;
    cursor: unset;

The `cursor` property is specified as zero or more `<url>` values, separated by commas, followed by a single mandatory [keyword value](#keyword_values). Each `<url>` should point to an image file. The browser will try to load the first image specified, falling back to the next if it can't, and falling back to the keyword value if no images could be loaded (or if none were specified).

Each `<url>` may be optionally followed by a pair of space-separated numbers, which represent `<x><y>` coordinates. These will set the cursor's hotspot, relative to the top-left corner of the image.

For example, this specifies two images using `<url>` values, providing `<x><y>` coordinates for the second one, and falling back to the `progress` keyword value if neither image can be loaded:

    cursor: url(one.svg), url(two.svg) 5 5, progress;

### Values

`<url>`  
A `url(…)` or a comma separated list `url(…), url(…), …`, pointing to an image file. More than one [`url()`](<url()>) may be provided as fallbacks, in case some cursor image types are not supported. A non-URL fallback (one or more of the keyword values) _must_ be at the end of the fallback list. See [Using URL values for the cursor property](css_basic_user_interface/using_url_values_for_the_cursor_property) for more details.

`<x>` `<y>` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Optional x- and y-coordinates. Two unitless nonnegative numbers less than 32.

<span id="Keyword_values">Keyword values</span>  
_Move your mouse over values to see their live appearance in your browser:_

Category

## Usage notes

Although the specification does not define any size limitations for `cursor`, individual [user agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may choose to do so. Cursor changes using images which are outside the size range supported by the browser will generally just be ignored.

Check the [Browser compatibility](#browser_compatibility) table for any notes on cursor size limits.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified, but with <a href="url()"><code>url()</code></a> values made absolute</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ [ <url> [ <x> <y> ]? , ]* [ auto | default | none | context-menu | help | pointer | progress | wait | cell | crosshair | text | vertical-text | alias | copy | move | no-drop | not-allowed | e-resize | n-resize | ne-resize | nw-resize | s-resize | se-resize | sw-resize | w-resize | ew-resize | ns-resize | nesw-resize | nwse-resize | col-resize | row-resize | all-scroll | zoom-in | zoom-out | grab | grabbing ] ]

## Examples

### Setting cursor types

    .foo {
      cursor: crosshair;
    }

    .bar {
      cursor: zoom-in;
    }

    /* A fallback keyword value is required when using a URL */
    .baz {
      cursor: url("hyper.cur"), auto;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ui-3/#cursor">CSS Basic User Interface Module Level 3<br />
<span class="small">The definition of 'cursor' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Addition of several keywords and the positioning syntax for <code>url()</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/ui.html#cursor-props">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'cursor' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`cursor`

1

12

1

Starting in Firefox 67, the maximum size allowed for custom cursors is 32x32 pixels due to cursors being misused by certain malicious sites.

4

In Internet Explorer 11, when `cursor` is applied to an element and this element is underneath an open [`<select>`](https://developer.mozilla.org/docs/Web/HTML/Element/select) menu and the user hovers over a [`<select>`](https://developer.mozilla.org/docs/Web/HTML/Element/select) menu item that's on top of said element, the cursor for said element will be displayed rather than the [`<select>`](https://developer.mozilla.org/docs/Web/HTML/Element/select)'s normal cursor. See [bug 817822](https://developer.microsoft.com/microsoft-edge/platform/issues/817822/).

7

1.2

No

18

No

14

1

1.0

`alias`

1

12

1.5

10

10.6

3

No

18

No

14

1

1.0

`all-scroll`

1

12

1.5

6

10.6

3

No

18

No

14

1

1.0

`auto`

1

12

1

4

7

1.2

No

18

No

14

1

1.0

`bidirectional_resize`

1

12

1.5

10

10.6

3

No

18

No

14

1

1.0

`cell`

1

12

1.5

10

10.6

3

No

18

No

14

1

1.0

`col-resize`

1

12

1.5

6

10.6

3

No

18

No

14

1

1.0

`context-menu`

1

This cursor is only supported on macOS and Linux.

12

1.5

This cursor is only supported on macOS and Linux.

10

10.6

3

No

18

This cursor is only supported on macOS and Linux.

No

14

This cursor is only supported on macOS and Linux.

1

1.0

This cursor is only supported on macOS and Linux.

`copy`

1

12

1.5

10

10.6

3

No

18

No

14

1

1.0

`crosshair`

1

12

1

4

7

1.2

No

18

No

14

1

1.0

`default`

1

12

1

4

7

1.2

No

18

No

14

1

1.0

`grab`

68

Chrome also continues to support the prefixed versions.

1

Chrome 22 added Windows support.

14

27

1.5

No

55

Opera also continues to support the prefixed versions.

15

Opera 22 added Windows support.

11

4

No

68

Chrome also continues to support the prefixed versions.

18

Chrome 22 added Windows support.

No

48

Opera also continues to support the prefixed versions.

14

Opera 22 added Windows support.

1

10.0

1.0

`help`

1

12

1

4

7

1.2

No

18

No

14

1

1.0

`inherit`

1

12

1

8

9

1.2

No

18

No

14

1

1.0

`move`

1

12

1

4

7

1.2

No

18

No

14

1

1.0

`no-drop`

1

12

1.5

6

10.6

3

No

18

No

14

1

1.0

`none`

5

12

3

9

15

5

No

18

No

14

4.2

1.0

`not-allowed`

1

12

1.5

6

10.6

3

No

18

No

14

1

1.0

`pointer`

1

12

1

6

7

1.2

No

18

No

14

1

1.0

`progress`

1

12

1

6

7

1.2

No

18

No

14

1

1.0

`row-resize`

1

12

1.5

6

10.6

3

No

18

No

14

1

1.0

`text`

1

12

1

4

7

1.2

No

18

No

14

1

1.0

`unidirectional_resize`

1

12

1

4

7

1.2

No

18

No

14

1

1.0

`url`

1

12

1.5

Firefox 4 added macOS support.

6

15

3

No

18

No

14

1

1.0

`url_positioning_syntax`

1

79

1.5

Firefox 4 added macOS support.

No

15

3

No

18

No

14

1

1.0

`vertical-text`

1

12

1.5

No

10.6

3

No

18

No

14

1

1.0

`wait`

1

12

1

4

7

1.2

No

18

No

14

1

1.0

`zoom`

37

1

12

24

1

No

24

15-23

9

3

No

37

18

No

24

14-24

1

3.0

1.0

## See also

- [Using URL values for the cursor property](css_basic_user_interface/using_url_values_for_the_cursor_property)
- [`pointer-events`](pointer-events)
- [`url()`](<url()>) function

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/cursor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/cursor</a>
