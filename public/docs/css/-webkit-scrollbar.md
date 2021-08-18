# ::-webkit-scrollbar

**Draft**

This page is not complete.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `::-webkit-scrollbar` CSS pseudo-element affects the style of an element's scrollbar.

`::-webkit-scrollbar` is only available in [Blink](https://www.chromium.org/blink)- and [WebKit](https://webkit.org)-based browsers (e.g., Chrome, Edge, Opera, Safari, all browsers on iOS, and [others](https://en.wikipedia.org/wiki/List_of_web_browsers#WebKit-based)).

## CSS Scrollbar Selectors

You can use the following pseudo-elements to customize various parts of the scrollbar for webkit browsers:

- `::-webkit-scrollbar` — the entire scrollbar.
- `::-webkit-scrollbar-button` — the buttons on the scrollbar (arrows pointing upwards and downwards).
- `::-webkit-scrollbar-thumb` — the draggable scrolling handle.
- `::-webkit-scrollbar-track` — the track (progress bar) of the scrollbar.
- `::-webkit-scrollbar-track-piece` — the part of the track (progress bar) not covered by the handle.
- `::-webkit-scrollbar-corner` — the bottom corner of the scrollbar, where both horizontal and vertical scrollbars meet.
- `::-webkit-resizer` — the draggable resizing handle that appears at the bottom corner of some elements.

## Syntax

{{CSSSyntax}}

## Examples

### CSS

    .visible-scrollbar, .invisible-scrollbar, .mostly-customized-scrollbar {
      display: block;
      width: 10em;
      overflow: auto;
      height: 2em;
    }

    .invisible-scrollbar::-webkit-scrollbar {
      display: none;
    }

    /* Demonstrate a "mostly customized" scrollbar
     * (won't be visible otherwise if width/height is specified) */
    .mostly-customized-scrollbar::-webkit-scrollbar {
      width: 5px;
      height: 8px;
      background-color: #aaa; /* or add it to the track */
    }

    /* Add a thumb */
    .mostly-customized-scrollbar::-webkit-scrollbar-thumb {
        background: #000;
    }

### HTML

    <div class="visible-scrollbar">
      Etiam sagittis sem sed lacus laoreet, eu fermentum eros auctor.
      Proin at nulla elementum, consectetur ex eget, commodo ante.
      Sed eros mi, bibendum ut dignissim et, maximus eget nibh. Phasellus
      blandit quam turpis, at mollis velit pretium ut. Nunc consequat
      efficitur ultrices. Nullam hendrerit posuere est. Nulla libero
      sapien, egestas ac felis porta, cursus ultricies quam. Vestibulum
      tincidunt accumsan sapien, a fringilla dui semper in. Vivamus
      consectetur ipsum a ornare blandit. Aenean tempus at lorem sit
      amet faucibus. Curabitur nibh justo, faucibus sed velit cursus,
      mattis cursus dolor. Pellentesque id pretium est. Quisque
      convallis nisi a diam malesuada mollis. Aliquam at enim ligula.
    </div>

    <div class="invisible-scrollbar">
    Thisisaveeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeerylongword
    </div>

    <div class="mostly-customized-scrollbar">
    Thisisaveeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeerylongword<br>
    And pretty tall<br>
    thing with weird scrollbars.<br>
    Who thought scrollbars could be made weeeeird?
    </div>

### Result

## Specifications

Not part of any standard.

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

`::-webkit-scrollbar`

2

79

No

See [bug 1432935](https://bugzil.la/1432935).

No

15

4

≤37

18

No

See [bug 1432935](https://bugzil.la/1432935).

14

3.2

1.0

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

`::-webkit-scrollbar`

2

79

No

See [bug 1432935](https://bugzil.la/1432935).

No

15

4

≤37

18

No

See [bug 1432935](https://bugzil.la/1432935).

14

3

1.0

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

`::-webkit-scrollbar`

2

79

No

See [bug 1432935](https://bugzil.la/1432935).

No

15

4

≤37

18

No

See [bug 1432935](https://bugzil.la/1432935).

14

3

1.0

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

`::-webkit-scrollbar`

2

79

No

See [bug 1432935](https://bugzil.la/1432935).

No

15

4

≤37

18

No

See [bug 1432935](https://bugzil.la/1432935).

14

3

1.0

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

`::-webkit-scrollbar`

2

79

No

See [bug 1432935](https://bugzil.la/1432935).

No

15

4

≤37

18

No

See [bug 1432935](https://bugzil.la/1432935).

14

3

1.0

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

`::-webkit-scrollbar`

2

79

No

See [bug 1432935](https://bugzil.la/1432935).

No

15

4

≤37

18

No

See [bug 1432935](https://bugzil.la/1432935).

14

3

1.0

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

`::-webkit-scrollbar`

2

79

No

See [bug 1432935](https://bugzil.la/1432935).

No

15

4

≤37

18

No

See [bug 1432935](https://bugzil.la/1432935).

14

3

1.0

BCD tables only load in the browser

### ::-webkit-scrollbar-button

BCD tables only load in the browser

### ::-webkit-scrollbar-thumb

BCD tables only load in the browser

### ::-webkit-scrollbar-track

BCD tables only load in the browser

### ::-webkit-scrollbar-track-piece

BCD tables only load in the browser

### ::-webkit-scrollbar-corner

BCD tables only load in the browser

### ::-webkit-resizer

BCD tables only load in the browser

## See also

- WebKit blog on [Styling Scrollbars](https://webkit.org/blog/363/styling-scrollbars/)
- [WebKit test](https://trac.webkit.org/export/41842/trunk/LayoutTests/scrollbars/overflow-scrollbar-combinations.html) for scrollbar styles mentioned above
- <span class="page-not-created">`-ms-overflow-style`</span>
- [`scrollbar-width`](scrollbar-width)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-scrollbar" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-scrollbar</a>
