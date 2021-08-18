# Using media queries

**Media queries** are useful when you want to modify your site or app depending on a device's general type (such as print vs. screen) or specific characteristics and parameters (such as screen resolution or browser [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) width).

Media queries are used for the following:

- To conditionally apply styles with the [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`@media`](../@media) and [`@import`](../@import) [at-rules.](../at-rule)
- To target specific media for the [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style), [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link), [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source), and other [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) elements with the `media=` attribute.
- To [test and monitor media states](testing_media_queries) using the [`Window.matchMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia) and [`MediaQueryList.addListener()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList/addListener) [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) methods.

**Note:** The examples on this page use CSS's `@media` for illustrative purposes, but the basic syntax remains the same for all types of media queries.

## Syntax

A media query is composed of an optional _media type_ and any number of _media feature_ expressions. Multiple queries can be combined in various ways by using _logical operators_. Media queries are case-insensitive.

A media query computes to true when the media type (if specified) matches the device on which a document is being displayed _and_ all media feature expressions compute as true. Queries involving unknown media types are always false.

**Note:** A style sheet with a media query attached to its [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) tag [will still download](https://scottjehl.github.com/CSS-Download-Tests/) even if the query returns false. Nevertheless, its contents will not apply unless and until the result of the query changes to true.

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

<table><thead><tr class="header"><th>Name</th><th>Summary</th><th>Notes</th></tr></thead><tbody><tr class="odd"><td><a href="../@media/any-hover"><code>any-hover</code></a></td><td>Does any available input mechanism allow the user to hover over elements?</td><td>Added in Media Queries Level 4.</td></tr><tr class="even"><td><a href="../@media/any-pointer"><code>any-pointer</code></a></td><td>Is any available input mechanism a pointing device, and if so, how accurate is it?</td><td>Added in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="../@media/aspect-ratio"><code>aspect-ratio</code></a></td><td>Width-to-height aspect ratio of the viewport</td><td></td></tr><tr class="even"><td><a href="../@media/color"><code>color</code></a></td><td>Number of bits per color component of the output device, or zero if the device isn't color</td><td></td></tr><tr class="odd"><td><a href="../@media/color-gamut"><code>color-gamut</code></a></td><td>Approximate range of colors that are supported by the user agent and output device</td><td>Added in Media Queries Level 4.</td></tr><tr class="even"><td><a href="../@media/color-index"><code>color-index</code></a></td><td>Number of entries in the output device's color lookup table, or zero if the device does not use such a table</td><td></td></tr><tr class="odd"><td><a href="../@media/device-aspect-ratio"><code>device-aspect-ratio</code></a> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Width-to-height aspect ratio of the output device</td><td>Deprecated in Media Queries Level 4.</td></tr><tr class="even"><td><a href="../@media/device-height"><code>device-height</code></a> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Height of the rendering surface of the output device</td><td>Deprecated in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="../@media/device-width"><code>device-width</code></a> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Width of the rendering surface of the output device</td><td>Deprecated in Media Queries Level 4.</td></tr><tr class="even"><td><a href="../@media/display-mode"><code>display-mode</code></a></td><td>The display mode of the application, as specified in the web app manifest's <a href="https://developer.mozilla.org/en-US/docs/Web/Manifest#display"><code>display</code></a> member</td><td>Defined in the <a href="https://w3c.github.io/manifest/#the-display-mode-media-feature">Web App Manifest spec</a>.</td></tr><tr class="odd"><td><a href="../@media/forced-colors"><code>forced-colors</code></a></td><td>Detect whether user agent restricts color palette</td><td>Added in Media Queries Level 5.</td></tr><tr class="even"><td><a href="../@media/grid"><code>grid</code></a></td><td>Does the device use a grid or bitmap screen?</td><td></td></tr><tr class="odd"><td><a href="../@media/height"><code>height</code></a></td><td>Height of the viewport</td><td></td></tr><tr class="even"><td><a href="../@media/hover"><code>hover</code></a></td><td>Does the primary input mechanism allow the user to hover over elements?</td><td>Added in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="../@media/inverted-colors"><code>inverted-colors</code></a></td><td>Is the user agent or underlying OS inverting colors?</td><td>Added in Media Queries Level 5.</td></tr><tr class="even"><td><a href="../@media/monochrome"><code>monochrome</code></a></td><td>Bits per pixel in the output device's monochrome frame buffer, or zero if the device isn't monochrome</td><td></td></tr><tr class="odd"><td><a href="../@media/orientation"><code>orientation</code></a></td><td>Orientation of the viewport</td><td></td></tr><tr class="even"><td><a href="../@media/overflow-block"><code>overflow-block</code></a></td><td>How does the output device handle content that overflows the viewport along the block axis?</td><td>Added in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="../@media/overflow-inline"><code>overflow-inline</code></a></td><td>Can content that overflows the viewport along the inline axis be scrolled?</td><td>Added in Media Queries Level 4.</td></tr><tr class="even"><td><a href="../@media/pointer"><code>pointer</code></a></td><td>Is the primary input mechanism a pointing device, and if so, how accurate is it?</td><td>Added in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="../@media/prefers-color-scheme"><code>prefers-color-scheme</code></a></td><td>Detect if the user prefers a light or dark color scheme</td><td>Added in Media Queries Level 5.</td></tr><tr class="even"><td><a href="../@media/prefers-contrast"><code>prefers-contrast</code></a></td><td>Detects if the user has requested the system increase or decrease the amount of contrast between adjacent colors</td><td>Added in Media Queries Level 5.</td></tr><tr class="odd"><td><a href="../@media/prefers-reduced-motion"><code>prefers-reduced-motion</code></a></td><td>The user prefers less motion on the page</td><td>Added in Media Queries Level 5.</td></tr><tr class="even"><td><a href="../@media/prefers-reduced-transparency"><code>prefers-reduced-transparency</code></a></td><td>The user prefers reduced transparency</td><td>Added in Media Queries Level 5.</td></tr><tr class="odd"><td><a href="../@media/resolution"><code>resolution</code></a></td><td>Pixel density of the output device</td><td></td></tr><tr class="even"><td><a href="../@media/scan"><code>scan</code></a></td><td>Scanning process of the output device</td><td></td></tr><tr class="odd"><td><a href="../@media/scripting"><code>scripting</code></a></td><td>Detects whether scripting (i.e. JavaScript) is available</td><td>Added in Media Queries Level 5.</td></tr><tr class="even"><td><a href="../@media/update-frequency"><code>update</code></a></td><td>How frequently the output device can modify the appearance of content</td><td>Added in Media Queries Level 4.</td></tr><tr class="odd"><td><a href="../@media/width"><code>width</code></a></td><td>Width of the viewport including width of scrollbar</td><td></td></tr></tbody></table>

### Logical operators

The _logical operators_ `not`, `and`, and `only` can be used to compose a complex media query. You can also combine multiple media queries into a single rule by separating them with commas.

#### `and`

The `and` operator is used for combining multiple media features together into a single media query, requiring each chained feature to return true in order for the query to be true. It is also used for joining media features with media types.

#### `not`

The `not` operator is used to negate a media query, returning true if the query would otherwise return false. If present in a comma-separated list of queries, it will only negate the specific query to which it is applied. If you use the `not` operator, you _must also_ specify a media type.

**Note:** In Level 3, the `not` keyword can't be used to negate an individual media feature expression, only an entire media query.

#### `only`

The `only` operator is used to apply a style only if an entire query matches, and is useful for preventing older browsers from applying selected styles. When not using `only`, older browsers would interpret the query `screen and (max-width: 500px)` as `screen`, ignoring the remainder of the query, and applying its styles on all screens. If you use the `only` operator, you _must also_ specify a media type.

#### `,` (comma)

Commas are used to combine multiple media queries into a single rule. Each query in a comma-separated list is treated separately from the others. Thus, if any of the queries in a list is true, the entire media statement returns true. In other words, lists behave like a logical `or` operator.

## Targeting media types

Media types describe the general category of a given device. Although websites are commonly designed with screens in mind, you may want to create styles that target special devices such as printers or audio-based screenreaders. For example, this CSS targets printers:

    @media print { ... }

You can also target multiple devices. For instance, this `@media` rule uses two media queries to target both screen and print devices:

    @media screen, print { ... }

See <a href="#media_types" class="internal">Media types</a> for a list of all media types. Because they describe devices in only very broad terms, just a few are available; to target more specific attributes, use _media features_ instead.

## Targeting media features

Media features describe the specific characteristics of a given [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent), output device, or environment. For instance, you can apply specific styles to widescreen monitors, computers that use mice, or to devices that are being used in low-light conditions. This example applies styles when the user's _primary_ input mechanism (such as a mouse) can hover over elements:

    @media (hover: hover) { ... }

Many media features are _range features_, which means they can be prefixed with "min-" or "max-" to express "minimum condition" or "maximum condition" constraints. For example, this CSS will apply styles only if your browser's [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) width is equal to or narrower than 12450px:

    @media (max-width: 12450px) { ... }

If you create a media feature query without specifying a value, the nested styles will be used as long as the feature's value is not zero (or `none`, in Level 4). For example, this CSS will apply to any device with a color screen:

    @media (color) { ... }

If a feature doesn't apply to the device on which the browser is running, expressions involving that media feature are always false. For example, the styles nested inside the following query will never be used, because no speech-only device has a screen aspect ratio:

    @media speech and (aspect-ratio: 11/5) { ... }

For more [media feature](#media_features) examples, please see the reference page for each specific feature.

## Creating complex media queries

Sometimes you may want to create a media query that depends on multiple conditions. This is where the _logical operators_ come in: `not`, `and`, and `only`. Furthermore, you can combine multiple media queries into a _comma-separated list_; this allows you to apply the same styles in different situations.

In the previous example, we've already seen the `and` operator used to group a media _type_ with a media _feature_. The `and` operator can also combine multiple media features into a single media query. The `not` operator, meanwhile, negates a media query, basically reversing its normal meaning. The `only` operator prevents older browsers from applying the styles.

**Note:** In most cases, the `all` media type is used by default when no other type is specified. However, if you use the `not` or `only` operators, you must explicitly specify a media type.

### Combining multiple types or features

The `and` keyword combines a media feature with a media type _or_ other media features. This example combines two media features to restrict styles to landscape-oriented devices with a width of at least 30 ems:

    @media (min-width: 30em) and (orientation: landscape) { ... }

To limit the styles to devices with a screen, you can chain the media features to the `screen` media type:

    @media screen and (min-width: 30em) and (orientation: landscape) { ... }

### Testing for multiple queries

You can use a comma-separated list to apply styles when the user's device matches any one of various media types, features, or states. For instance, the following rule will apply its styles if the user's device has either a minimum height of 680px _or_ is a screen device in portrait mode:

    @media (min-height: 680px), screen and (orientation: portrait) { ... }

Taking the above example, if the user had a printer with a page height of 800px, the media statement would return true because the first query would apply. Likewise, if the user were on a smartphone in portrait mode with a viewport height of 480px, the second query would apply and the media statement would still return true.

### Inverting a query's meaning

The `not` keyword inverts the meaning of an entire media query. It will only negate the specific media query it is applied to. (Thus, it will not apply to every media query in a comma-separated list of media queries.) The `not` keyword can't be used to negate an individual feature query, only an entire media query. The `not` is evaluated last in the following query:

    @media not all and (monochrome) { ... }

... so that the above query is evaluated like this:

    @media not (all and (monochrome)) { ... }

... rather than like this:

    @media (not all) and (monochrome) { ... }

As another example, the following media query:

    @media not screen and (color), print and (color) { ... }

... is evaluated like this:

    @media (not (screen and (color))), print and (color) { ... }

### Improving compatibility with older browsers

The `only` keyword prevents older browsers that do not support media queries with media features from applying the given styles. _It has no effect on modern browsers._

    @media only screen and (color) { ... }

## Syntax improvements in Level 4

The Media Queries Level 4 specification includes some syntax improvements to make media queries using features that have a "range" type, for example width or height, less verbose. Level 4 adds a _range context_ for writing such queries. For example, using the `max-` functionality for width we might write the following:

**Note:** The Media Queries Level 4 specification has reasonable support in modern browsers, but some media features are not well supported. See the [`@media` browser compatibility table](../@media#browser_compatibility) for more details.

    @media (max-width: 30em) { ... }

In Media Queries Level 4 this can be written as:

    @media (width <= 30em) { ... }

Using `min-` and `max-` we might test for a width between two values like so:

    @media (min-width: 30em) and (max-width: 50em) { ... }

This would convert to the Level 4 syntax as:

    @media (30em <= width <= 50em ) { ... }

Media Queries Level 4 also adds ways to combine media queries using full boolean algebra with **and**, **not**, and **or**.

### Negating a feature with `not`

Using `not()` around a media feature negates that feature in the query. For example, `not(hover)` would match if the device had no hover capability:

    @media (not(hover)) { ... }

### Testing for multiple features with `or`

You can use `or` to test for a match among more than one feature, resolving to `true` if any of the features are true. For example, the following query tests for devices that have a monochrome display or hover capability:

    @media (not (color)) or (hover) { ... }

## See also

- [Testing media queries programmatically](testing_media_queries)
- [CSS Animations Between Media Queries](https://davidwalsh.name/animate-media-queries)
- [Extended Mozilla media features](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions#media_features)
- [Extended WebKit media features](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions#media_features)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries</a>
