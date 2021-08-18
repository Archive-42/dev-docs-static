# content

The `content` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property replaces an element with a generated value. Objects inserted using the `content` property are **anonymous [replaced elements](replaced_element)\***.\*

    /* Keywords that cannot be combined with other values */
    content: normal;
    content: none;

    /* <image> values */
    content: url("http://www.example.com/test.png");
    content: linear-gradient(#e66465, #9198e5);
    content: image-set("image1x.png" 1x, "image2x.png" 2x);

    /* alt text for generated content, added in the Level 3 specification */
    content: url("http://www.example.com/test.png") / "This is the alt text";

    /* <string> value */
    content: "prefix";

    /* <counter> values, optionally with <list-style-type> */
    content: counter(chapter_counter);
    content: counter(chapter_counter, upper-roman);
    content: counters(section_counter, ".");
    content: counters(section_counter, ".", decimal-leading-zero);

    /* attr() value linked to the HTML attribute value */
    content: attr(value string);

    /* Language- and position-dependent keywords */
    content: open-quote;
    content: close-quote;
    content: no-open-quote;
    content: no-close-quote;

    /* Except for normal and none, several values can be used simultaneously */
    content: open-quote counter(chapter_counter);

    /* Global values */
    content: inherit;
    content: initial;
    content: unset;

## Syntax

### Values

`none`  
The pseudo-element is not generated.

`normal`  
Computes to `none` for the `::before` and `::after` pseudo-elements.

[`<string>`](string)  
Specifies the "alt text" for the element. This value can be any number of text characters. Non-Latin characters must be encoded using their Unicode escape sequences: for example, `\000A9` represents the copyright symbol.

[`<image>`](image)  
An [`<image>`](image), denoted by the [`url()`](<url()>) or [`<gradient>`](gradient) data type, or part of the webpage, defined by the [`element()`](<element()>) function, denoting the content to display.

[`counter()`](<counter()>)  
The value of a [CSS counter](css_lists_and_counters/using_css_counters), generally a number produced by computations defined by [`<counter-reset>`](counter-reset) and [`<counter-increment>`](counter-increment) properties. It can be displayed using either the [`counter()`](<counter()>) or [`counters()`](<counters()>) function.

The [`counter()`](<counter()>) function has two forms: 'counter(name)' or 'counter(name, style)'. The generated text is the value of the innermost counter of the given name in scope at the given pseudo-element. It is formatted in the specified [`<list-style-type>`](list-style-type) (`decimal` by default).

The [`counters()`](<counters()>) function also has two forms: 'counters(name, string)' or 'counters(name, string, style)'. The generated text is the value of all counters with the given name in scope at the given pseudo-element, from outermost to innermost, separated by the specified string. The counters are rendered in the indicated [`<list-style-type>`](list-style-type) (`decimal` by default).

`attr(x)`  
The value of the element's attribute `x` as a string. If there is no attribute `x`, an empty string is returned. The case-sensitivity of attribute names depends on the document language.

`open-quote` | `close-quote`  
These values are replaced by the appropriate string from the [`quotes`](quotes) property.

`no-open-quote` | `no-close-quote`  
Introduces no content, but increments (decrements) the level of nesting for quotes.

## Accessibility concerns

CSS-generated content is not included in the [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction). Because of this, it will not be represented in the [accessibility tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis) and certain assistive technology/browser combinations will not announce it. If the content conveys information that is critical to understanding the page's purpose, it is better to include it in the main document.

- [Accessibility support for CSS generated content – Tink](https://tink.uk/accessibility-support-for-css-generated-content/)
- [Explanation of WCAG, Guideline 1.3 – MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.3_%e2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>All elements, tree-abiding pseudo-elements, and page margin boxes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>On elements, always computes to <code>normal</code>. On <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a>, if <code>normal</code> is specified, computes to <code>none</code>. Otherwise, for URI values, the absolute URI; for <code>attr()</code> values, the resulting string; for other keywords, as specified.</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | none | [ <content-replacement> | <content-list> ] [/ <string> ]?where
    <content-replacement> = <image>
    <content-list> = [ <string> | contents | <image> | <quote> | <target> | <leader()> ]+where
    <image> = <url> | <image()> | <image-set()> | <element()> | <paint()> | <cross-fade()> | <gradient>
    <quote> = open-quote | close-quote | no-open-quote | no-close-quote
    <target> = <target-counter()> | <target-counters()> | <target-text()>
    <leader()> = leader( <leader-type> )where
    <image()> = image( <image-tags>? [ <image-src>? , <color>? ]! )
    <image-set()> = image-set( <image-set-option># )
    <element()> = element( <id-selector> )
    <paint()> = paint( <ident>, <declaration-value>? )
    <cross-fade()> = cross-fade( <cf-mixing-image> , <cf-final-image>? )
    <gradient> = <linear-gradient()> | <repeating-linear-gradient()> | <radial-gradient()> | <repeating-radial-gradient()> | <conic-gradient()>
    <target-counter()> = target-counter( [ <string> | <url> ] , <custom-ident> , <counter-style>? )
    <target-counters()> = target-counters( [ <string> | <url> ] , <custom-ident> , <string> , <counter-style>? )
    <target-text()> = target-text( [ <string> | <url> ] , [ content | before | after | first-letter ]? )
    <leader-type> = dotted | solid | space | <string>where
    <image-tags> = ltr | rtl
    <image-src> = <url> | <string>
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>
    <image-set-option> = [ <image> | <string> ] <resolution>
    <id-selector> = <hash-token>
    <cf-mixing-image> = <percentage>? && <image>
    <cf-final-image> = <image> | <color>
    <linear-gradient()> = linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )
    <repeating-linear-gradient()> = repeating-linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )
    <radial-gradient()> = radial-gradient( [ <ending-shape> || <size> ]? [ at <position> ]? , <color-stop-list> )
    <repeating-radial-gradient()> = repeating-radial-gradient( [ <ending-shape> || <size> ]? [ at <position> ]? , <color-stop-list> )
    <conic-gradient()> = conic-gradient( [ from <angle> ]? [ at <position> ]?, <angular-color-stop-list> )
    <counter-style> = <counter-style-name> | symbols()where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <side-or-corner> = [ left | right ] || [ top | bottom ]
    <color-stop-list> = [ <linear-color-stop> [, <linear-color-hint>]? ]# , <linear-color-stop>
    <ending-shape> = circle | ellipse
    <size> = closest-side | farthest-side | closest-corner | farthest-corner | <length> | <length-percentage>{2}
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]
    <angular-color-stop-list> = [ <angular-color-stop> [, <angular-color-hint>]? ]# , <angular-color-stop>
    <counter-style-name> = <custom-ident>where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>
    <linear-color-stop> = <color> <color-stop-length>?
    <linear-color-hint> = <length-percentage>
    <length-percentage> = <length> | <percentage>
    <angular-color-stop> = <color> && <color-stop-angle>?
    <angular-color-hint> = <angle-percentage>where
    <color-stop-length> = <length-percentage>{1,2}
    <color-stop-angle> = <angle-percentage>{1,2}
    <angle-percentage> = <angle> | <percentage>

## Examples

### Headings and quotes

This example inserts quotation marks around quotes, and adds the word "Chapter" before headings.

#### HTML

    <h1>5</h1>
    <p>According to Sir Tim Berners-Lee,
      <q cite="http://www.w3.org/People/Berners-Lee/FAQ.html#Internet">I was
        lucky enough to invent the Web at the time when the Internet
        already existed - and had for a decade and a half.</q>
      We must understand that there is nothing fundamentally wrong
      with building on the contributions of others.
    </p>

    <h1>6</h1>
    <p>According to the Mozilla Manifesto,
      <q cite="http://www.mozilla.org/en-US/about/manifesto/">Individuals
        must have the ability to shape the Internet and
        their own experiences on the Internet.</q>
      Therefore, we can infer that contributing to the open web
      can protect our own individual experiences on it.
    </p>

#### CSS

    q {
      color: blue;
    }

    q::before {
      content: open-quote;
    }

    q::after {
      content: close-quote;
    }

    h1::before  {
      content: "Chapter ";  /* The trailing space creates separation
                               between the added content and the
                               rest of the content */
    }

#### Result

### Image combined with text

This example inserts an image before the link. If the image is not found, it inserts text instead.

#### HTML

    <a href="https://www.mozilla.org/en-US/">Mozilla Home Page</a>

#### CSS

    a::before {
      content: url("https://mozorg.cdn.mozilla.net/media/img/favicon.ico") / " MOZILLA: ";
      font: x-small Arial, sans-serif;
      color: gray;
    }

#### Result

### Targeting classes

This example inserts additional text after special items in a list.

#### HTML

    <h2>Paperback Best Sellers</h2>
    <ol>
      <li>Political Thriller</li>
      <li class="new-entry">Halloween Stories</li>
      <li>My Biography</li>
      <li class="new-entry">Vampire Romance</li>
    </ol>

#### CSS

    .new-entry::after {
      content: " New!";  /* The leading space creates separation
                            between the added content and the
                            rest of the content */
      color: red;
    }

#### Result

### Images and element attributes

This example inserts an image before each link, and adds its `id` attribute after.

#### HTML

    <ul>
      <li><a id="moz" href="https://www.mozilla.org/">
        Mozilla Home Page</a></li>
      <li><a id="mdn" href="https://developer.mozilla.org/">
        Mozilla Developer Network</a></li>
    </ul>

#### CSS

    a {
      text-decoration: none;
      border-bottom: 3px dotted navy;
    }

    a::after {
      content: " (" attr(id) ")";
    }

    #moz::before {
      content: url("https://mozorg.cdn.mozilla.net/media/img/favicon.ico");
    }

    #mdn::before {
      content: url("https://mdn.mozillademos.org/files/7691/mdn-favicon16.png");
    }

    li {
      margin: 1em;
    }

#### Result

### Element replacement

This example replaces an element's content with an image. You can replace the contents of an element with either a [`url()`](<url()>) or an [`<image>`](image) value. Content added with `::before` or `::after` will not be generated as the contents of the element have been replaced.

#### HTML

    <div id="replaced">Mozilla</div>

#### CSS

    #replaced {
      content: url("https://mdn.mozillademos.org/files/12668/MDN.svg");
    }

    #replaced::after { /* will not show if element replacement is supported */
      content: " (" attr(id) ")";
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-content-3/#content-property">CSS Generated Content Module Level 3<br />
<span class="small">The definition of 'content' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds support for alt-text</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/generate.html#content">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'content' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`content`

1

12

1

8

4

1

1

18

4

10.1

1

1.0

`alt_text`

77

79

No

No

64

No

77

77

No

55

No

12.0

`element_replacement`

28

79

63

No

7

9

≤37

28

63

10.1

9

1.5

`url`

1

12

1

8

7

1

37

18

4

14

1

1.0

## See also

- [Replaced elements](replaced_element)
- [`::after`](::after)
- [`::before`](::before)
- [`::marker`](::marker)
- [`quotes`](quotes)
- [`url()`](<url()>) function

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/content" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/content</a>
