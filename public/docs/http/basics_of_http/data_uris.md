Data URIs
=========

**Data URLs**, URLs prefixed with the `data:` scheme, allow content creators to embed small files inline in documents. They were formerly known as "data URIs" until that name was retired by the WHATWG.

**Note**: Data URLs are treated as unique opaque origins by modern browsers, rather than inheriting the origin of the settings object responsible for the navigation.

Syntax
------

Data URLs are composed of four parts: a prefix (`data:`), a [MIME type](mime_types) indicating the type of data, an optional `base64` token if non-textual, and the data itself:

    data:[<mediatype>][;base64],<data>

The `mediatype` is a [MIME type](mime_types) string, such as `'image/jpeg'` for a JPEG image file. If omitted, defaults to `text/plain;charset=US-ASCII`

If the data is textual, you can simply embed the text (using the appropriate entities or escapes based on the enclosing document's type). Otherwise, you can specify `base64` to embed base64-encoded binary data. You can find more info on MIME types [here](mime_types) and [here](mime_types/complete_list_of_mime_types).

A few examples:

`data:,Hello%2C%20World!`  
Simple text/plain data. Note the use of [percent-encoding](https://developer.mozilla.org/en-US/docs/Glossary/percent-encoding) (URL-encoding) for the quote and space characters. Also, for CSV data (MIME type "text/csv"), percent-encoding is needed to preserve the line endings that delimit rows of the spreadsheet.

`data:text/plain;base64,SGVsbG8sIFdvcmxkIQ==`  
base64-encoded version of the above

`data:text/html,%3Ch1%3EHello%2C%20World!%3C%2Fh1%3E`  
An HTML document with `<h1>Hello, World!</h1>`

`data:text/html,<script>alert('hi');</script>`  
An HTML document that executes a JavaScript alert. Note that the closing script tag is required.

Encoding data into base64 format
--------------------------------

Base64 is a group of binary-to-text encoding schemes that represent binary data in an ASCII string format by translating it into a radix-64 representation. By consisting only in ASCII characters, base64 strings are generally url-safe, and that's why they can be used to encode data in Data URLs.

### Encoding in Javascript

The Web APIs have native methods to encode or decode to base64: [Base64 encoding and decoding](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64/Base64_encoding_and_decoding).

### Encoding on a Unix system

Base64 encoding of a file or string on Linux and Mac OS X systems can be achieved using the command-line `base64` (or, as an alternative, the `uuencode` utility with `-m` argument).

    echo -n hello|base64
    # outputs to console: aGVsbG8=

    echo -n hello>a.txt
    base64 a.txt
    # outputs to console: aGVsbG8=

    base64 a.txt>b.txt
    # outputs to file b.txt: aGVsbG8=

### Encoding on Microsoft Windows

Encoding on Windows can be done through powershell or some dedicated tool. It can even be done via bash `base64` utility (see section Encoding on a Unix system) if [WSL](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux) is activated.

    [convert]::ToBase64String([Text.Encoding]::UTF8.GetBytes("hello"))
    # outputs to console: aGVsbG8=

    bash -c "echo -n hello`|base64"
    # outputs to console: aGVsbG8=
    # the backtick (`) is used to escape the piping (|) character here

Common problems
---------------

This section describes problems that commonly occur when creating and using `data` URLs.

    data:text/html,lots of text...<p><a name%3D"bottom">bottom</a>?arg=val

This represents an HTML resource whose contents are:

    lots of text...<p><a name="bottom">bottom</a>?arg=val

Syntax  
The format for `data` URLs is very simple, but it's easy to forget to put a comma before the "data" segment, or to incorrectly encode the data into base64 format.

Formatting in HTML  
A `data` URL provides a file within a file, which can potentially be very wide relative to the width of the enclosing document. As a URL, the `data` should be formatable with whitespace (linefeed, tab, or spaces), but there are practical issues that arise [when using base64 encoding](http://bugzilla.mozilla.org/show_bug.cgi?id=73026#c12).

Length limitations  
Although Firefox supports `data` URLs of essentially unlimited length, browsers are not required to support any particular maximum length of data. For example, the Opera 11 browser limited URLs to 65535 characters long which limits `data` URLs to 65529 characters (65529 characters being the length of the encoded data, not the source, if you use the plain `data:`, without specifying a MIME type).

Lack of error handling  
Invalid parameters in media, or typos when specifying `'base64'`, are ignored, but no error is provided.

No support for query strings, etc.  
The data portion of a data URL is opaque, so an attempt to use a query string (page-specific parameters, with the syntax `<url>?parameter-data`) with a data URL will just include the query string in the data the URL represents.

Security issues  
A number of security issues (e.g. phishing) have been associated with data URLs, and navigating to them in the browser's top level. To mitigate such issues, top-level navigation to `data://` URLs has been blocked in Firefox 59+ (release version, Nightly/Beta from 58), and we hope to see other browsers follow suit soon. [See Blocking Top-Level Navigations to data URLs for Firefox 58](https://blog.mozilla.org/security/2017/11/27/blocking-top-level-navigations-data-urls-firefox-58/) for more details.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc2397">RFC 2397</a></td><td>The "data" URL scheme</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

data URL scheme

Yes

12

 12   
The maximum size supported is 4GB

Yes

8

 8   
The maximum size supported is 32kB

7.2

Yes

CSS files

Yes

12

 12   
The maximum size supported is 4GB

Yes

8

 8   
The maximum size supported is 32kB

 9   
The maximum size supported is 4GB

7.2

Yes

HTML files

Yes

79

Yes

No

Yes

Yes

JavaScript files

Yes

12

 12   
The maximum size supported is 4GB

Yes

9

 9   
The maximum size supported is 4GB

7.2

Yes

Top-level navigation blocked to data:// URIs

60

≤79

59

No

47

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

data URL scheme

Yes

Yes

Yes

Yes

Yes

Yes

CSS files

Yes

Yes

Yes

Yes

Yes

Yes

HTML files

Yes

Yes

Yes

Yes

Yes

Yes

JavaScript files

Yes

Yes

Yes

Yes

Yes

Yes

Top-level navigation blocked to data:// URIs

No

60

59

44

?

8.0

See also
--------

-   [Base64 encoding and decoding](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64/Base64_encoding_and_decoding)
-   [Percent encoding](https://developer.mozilla.org/en-US/docs/Glossary/percent-encoding)
-   [`atob()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64/atob)
-   [`btoa()`](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64/btoa)
-   [CSS `url()`](https://developer.mozilla.org/en-US/docs/Web/CSS/uri)
-   [URI](https://developer.mozilla.org/en-US/docs/Glossary/URI)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs</a>
