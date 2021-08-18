Content-Language
================

The `Content-Language` [entity header](https://developer.mozilla.org/en-US/docs/Glossary/entity_header) is used to **describe the language(s) intended for the audience**, so that it allows a user to differentiate according to the users' own preferred language.

For example, if "`Content-Language: de-DE`" is set, it says that the document is intended for German language speakers (however, it doesn't indicate the document is written in German. For example, it might be written in English as part of a language course for German speakers. If you want to indicate which language the document is written in, use the [`lang` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/lang) instead).

If no `Content-Language` is specified, the default is that the content is intended for all language audiences. Multiple language tags are also possible, as well as applying the `Content-Language` header to various media types and not only to textual documents.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Entity_header">Entity header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_response_header">CORS-safelisted response header</a></td><td>yes</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header">CORS-safelisted request header</a></td><td>yes, with the additional restriction that values can only be <code>0-9</code>, <code>A-Z</code>, <code>a-z</code>, space or <code>*,-.;=</code>.</td></tr></tbody></table>

Syntax
------

    Content-Language: de-DE
    Content-Language: en-US
    Content-Language: de-DE, en-CA

Directives
----------

`language-tag`  
Multiple language tags are separated by comma. Each language tag is a sequence of one or more case-insensitive subtags, each separated by a hyphen character ("`-`", `%x2D`). In most cases, a language tag consists of a primary language subtag that identifies a broad family of related languages (e.g., "`en`" = English), which is optionally followed by a series of subtags that refine or narrow that language's range (e.g., "`en-CA`" = the variety of English as communicated in Canada).

**Note:** Language tags are formaly defined in [RFC 5646](https://tools.ietf.org/html/rfc5646), which rely on the [ISO 639](https://en.wikipedia.org/wiki/ISO_639) standard (quite often the [ISO 639-1 code list](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)) for [language codes](https://en.wikipedia.org/wiki/Language_code) to be used.

Examples
--------

### Indicating the language a document is written in

The global `lang` attribute is used on HTML elements to indicate the language of an entire [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) document or parts of it.

    <html lang="de">

Do **not** use this meta element like this for stating a document language:

    <!-- /!\ This is bad practice -->
    <meta http-equiv="content-language" content="de">

### Indicating a target audience for a resource

The `Content-Language` header is used to specify the **intended audience of the page**, and can indicate that this is more than one language.

    Content-Language: de, en

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-3.1.3.2">RFC 7231, section 3.1.3.2: Content-Language</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Content-Language`

Yes

12

Yes

Yes

Yes

Yes

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Content-Language`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Accept-Language`](accept-language)
-   [HTTP headers, meta elements and language information](https://www.w3.org/International/questions/qa-http-and-lang.en)
-   [HTML `lang` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/lang)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Language$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Language" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Language</a>
