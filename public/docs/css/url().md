# url()

The `url()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) is used to include a file. The parameter is an absolute URL, a relative URL, or a data URI. The `url()` function can be passed as a parameter of another CSS functions, like the [`attr()`](<attr()>) function. Depending on the property for which it is a value, the resource sought can be an image, font, or a stylesheet. The `url()` functional notation is the value for the `<url>` data type.

**URI or URL?** There is a difference between a [URI](https://developer.mozilla.org/en-US/docs/Glossary/URI) and a [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL). A URI identifies a resource. A URL is a type of URI, and describes the _location_ of a resource. A URI can be either a URL or a name ([URN](https://developer.mozilla.org/en-US/docs/Glossary/URN)) of a resource.

In CSS Level 1, the `url()` functional notation described only true URLs. In CSS Level 2, the definition of `url()` was extended to describe any URI, whether a URL or a URN. Confusingly, this meant that `url()` could be used to create a `<uri>` CSS data type. This change was not only awkward but, debatably, unnecessary, since URNs are almost never used in actual CSS. To alleviate the confusion, CSS Level 3 returned to the narrower, initial definition. Now, `url()` denotes only true `<url>`s.

    /* Simple usage */
    url(https://example.com/images/myImg.jpg);
    url(data:image/png;base64,iRxVB0…);
    url(myFont.woff);
    url(#IDofSVGpath);

    /* associated properties */
    background-image: url("https://mdn.mozillademos.org/files/16761/star.gif");
    list-style-image: url('../images/bullet.jpg');
    content: url("pdficon.jpg");
    cursor: url(mycursor.cur);
    border-image-source: url(/media/diamonds.png);
    src: url('fantasticfont.woff');
    offset-path: url(#path);
    mask-image: url("masks.svg#mask1");

    /* Properties with fallbacks */
    cursor: url(pointer.cur), pointer;

    /* Associated short-hand properties */
    background: url('https://mdn.mozillademos.org/files/16761/star.gif') bottom right repeat-x blue;
    border-image: url("/media/diamonds.png") 30 fill / 30px / 30px space;

    /* As a parameter in another CSS function */
    background-image: cross-fade(20% url(first.png), url(second.png));
    mask-image: image(url(mask.png), skyblue, linear-gradient(rgba(0, 0, 0, 1.0), transparent);

    /* as part of a non-shorthand multiple value */
    content: url(star.svg) url(star.svg) url(star.svg) url(star.svg) url(star.svg);

    /* at-rules */
    @document url("https://www.example.com/") { ... }
        This is an experimental API that should not be used in production code.


    @import url("https://www.example.com/style.css");
    @namespace url(http://www.w3.org/1999/xhtml);

Relative URLs, if used, are relative to the URL of the stylesheet (not to the URL of the web page).

The `url()` function can be included as a value for [`background`](background), [`background-image`](background-image), [`list-style`](list-style), [`list-style-image`](list-style-image), [`content`](content), [`cursor`](cursor), [`border`](border), [`border-image`](border-image), [`border-image-source`](border-image-source), [`mask`](mask), [`mask-image`](mask-image), [src](@font-face/src) as part of a [@font-face](@font-face) block, and [@counter-style/symbol](@counter-style/symbols)

## Syntax

### Values

`<string>`  
&lt;url&gt;  
A url, which is a relative or absolute address, or pointer, to the web resource to be included, or a data uri, optionally in single or double quotes. Quotes are required if the URL includes parentheses, whitespace, or quotes, unless these characters are escaped, or if the address includes control characters above 0x7e. Double quotes cannot occur inside double quotes and single quotes cannot occur inside single quotes unless escaped. The following are all valid and equivalent:

    <css_property>: url("https://example.com/image.png")
    <css_property>: url('https://example.com/image.png')
    <css_property>: url(https://example.com/image.png)

If you choose to write the URL without quotes, use a backslash (`\`) before any parentheses, whitespace characters, single quotes (`'`) and double quotes (`"`) that are part of the URL.

path  
References the ID of an [SVG shape](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Basic_Shapes) -- `circle`, `ellipse`, `line`, `path`, `polygon`, `polyline`, or `rect` -- using the shape's geometry as the path.

`<url-modifier>` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
In the future, the `url()` function may support specifying a modifier, an identifier or a functional notation, which alters the meaning of the URL string.This is not supported and not fully defined in the specification.

### Formal syntax

    url( <string> <url-modifier>* )

## Examples

### A url used in the background property

    .topbanner {
      background: url("topbanner.png") #00D no-repeat fixed;
    }

### A url loading an image as a list bullet

    ul {
      list-style: square url(http://www.example.com/redball.png);
    }

### Usage in the content property

#### HTML

    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ul>

#### CSS

    li::after {
      content: ' - ' url(https://mdn.mozillademos.org/files/16761/star.gif);
    }

#### Result

### Using a data-uri

#### HTML

    <div class="background"></div>

#### CSS

    .background {
      background: yellow;
      background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='90' height='45'%3E%3Cpath d='M10 10h60' stroke='%2300F' stroke-width='5'/%3E%3Cpath d='M10 20h60' stroke='%230F0' stroke-width='5'/%3E%3Cpath d='M10 30h60' stroke='red' stroke-width='5'/%3E%3C/svg%3E");
    }

### Usage in filters

When a URL is used as a path for a filter, the URL must be one of the following:

1.  The path to an SVG file with the ID of the filter appended.
2.  the ID of the filter, if the SVG already exists on the page.

<!-- -->

    .blur {
      filter: url(my-file.svg#svg-blur); /* the URL of an SVG file used as a filter */
    }

    .inline-blur {
      filter: url(#svg-blur); /* the ID of an SVG that is embedded in the HTML page */
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#urls">CSS Values and Units Module Level 4<br />
<span class="small">The definition of 'url()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#urls">CSS Values and Units Module Level 3<br />
<span class="small">The definition of 'url()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant change from CSS Level 2 (Revision 1).</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/syndata.html#uri">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'uri()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant change from CSS Level 1.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#url">CSS Level 1<br />
<span class="small">The definition of 'url()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`url()`

1

12

1

3

3.5

1

1

18

4

14

1

1.0

## See also

- [`<gradient>`](gradient)
- [`element()`](<element()>)
- [`image()`](<image()>)
- [`image-set()`](<image-set()>)
- [`cross-fade()`](<cross-fade()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/url()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/url()</a>
