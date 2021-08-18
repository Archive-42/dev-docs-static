Content-Disposition
===================

In a regular HTTP response, the `Content-Disposition` response header is a header indicating if the content is expected to be displayed *inline* in the browser, that is, as a Web page or as part of a Web page, or as an *attachment*, that is downloaded and saved locally.

In a `multipart/form-data` body, the HTTP `Content-Disposition` general header is a header that must be used on each subpart of a multipart body to give information about the field it applies to. The subpart is delimited by the *boundary* defined in the [`Content-Type`](content-type) header. Used on the body itself, `Content-Disposition` has no effect.

The `Content-Disposition` header is defined in the larger context of MIME messages for e-mail, but only a subset of the possible parameters apply to HTTP forms and [`POST`](../methods/post) requests. Only the value `form-data`, as well as the optional directive `name` and `filename`, can be used in the HTTP context.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a> (for the main body)<br />
<a href="https://developer.mozilla.org/en-US/docs/Glossary/General_header">General header</a> (for a subpart of a multipart body)</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

### As a response header for the main body

The first parameter in the HTTP context is either `inline` (default value, indicating it can be displayed inside the Web page, or as the Web page) or `attachment` (indicating it should be downloaded; most browsers presenting a 'Save as' dialog, prefilled with the value of the `filename` parameters if present).

    Content-Disposition: inline
    Content-Disposition: attachment
    Content-Disposition: attachment; filename="filename.jpg"

**Notes:** Chrome, and Firefox 82 and later, prioritize the HTML [&lt;a&gt; element's](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) `download` attribute over the `Content-Disposition` `inline` parameter (for [same-origin URLs](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy)). Earlier Firefox versions prioritize the header and will display the content inline.

### As a header for a multipart body

A `multipart/form-data` body requires a `Content-Disposition` header to provide information for each subpart of the form (e.g. for every form field and any files that are part of field data). The first directive is always `form-data`, and the header *must* also include a `name` parameter to identify the relevant field. Additional directives are case-insensitive and have arguments that use quoted-string syntax after the `'='` sign. Multiple parameters are separated by a semi-colon (`';'`).

    Content-Disposition: form-data; name="fieldName"
    Content-Disposition: form-data; name="fieldName"; filename="filename.jpg"

### Directives

`name`  
Is followed by a string containing the name of the HTML field in the form that the content of this subpart refers to. When dealing with multiple files in the same field (for example, the `multiple` attribute of an `<input type="file">` element), there can be several subparts with the same name.

A `name` with a value of `'_charset_'` indicates that the part is not an HTML field, but the default charset to use for parts without explicit charset information.

`filename`  
Is followed by a string containing the original name of the file transmitted. The filename is always optional and must not be used blindly by the application: path information should be stripped, and conversion to the server file system rules should be done. This parameter provides mostly indicative information. When used in combination with `Content-Disposition: attachment`, it is used as the default filename for an eventual "Save As" dialog presented to the user.

`filename*`  
The parameters `filename` and `filename*` differ only in that `filename*` uses the encoding defined in [RFC 5987](https://tools.ietf.org/html/rfc5987). When both `filename` and `filename*` are present in a single header field value, `filename*` is preferred over `filename` when both are understood.

The string following `filename` should always be put into quotes; but, for compatibility reasons, many browsers try to parse unquoted names that contain spaces.

Examples
--------

A response triggering the "Save As" dialog:

    200 OK
    Content-Type: text/html; charset=utf-8
    Content-Disposition: attachment; filename="cool.html"
    Content-Length: 21

    <HTML>Save me!</HTML>

This simple HTML file will be saved as a regular download rather than displayed in the browser. Most browsers will propose to save it under the `cool.html` filename (by default).

An example of an HTML form posted using the `multipart/form-data` format that makes use of the `Content-Disposition` header:

    POST /test.html HTTP/1.1
    Host: example.org
    Content-Type: multipart/form-data;boundary="boundary"

    --boundary
    Content-Disposition: form-data; name="field1"

    value1
    --boundary
    Content-Disposition: form-data; name="field2"; filename="example.txt"

    value2
    --boundary--

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7578">RFC 7578</a></td><td>Returning Values from Forms: multipart/form-data</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc6266">RFC 6266</a></td><td>Use of the Content-Disposition Header Field in the Hypertext Transfer Protocol (HTTP)</td></tr><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc2183">RFC 2183</a></td><td>Communicating Presentation Information in Internet Messages: The Content-Disposition Header Field</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Content-Disposition`

Yes

12

Yes

 Yes   
From version 82, if an `<a>` element's `download` attribute is set (for a same-origin URL) then the `inline` directive is ignored. Earlier versions did not match the specification and respected the header directive over the attribute. See [bug 1658877](https://bugzil.la/1658877).

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

`Content-Disposition`

Yes

Yes

Yes

 Yes   
From version 82, if an `<a>` element's `download` attribute is set (for a same-origin URL) then the `inline` directive is ignored. Earlier versions did not match the specification and respected the header directive over the attribute. See [bug 1658877](https://bugzil.la/1658877).

Yes

Yes

Yes

Compatibility notes
-------------------

-   Firefox 5 handles the `Content-Disposition` HTTP response header more effectively if both the `filename` and `filename*` parameters are provided; it looks through all provided names, using the `filename*` parameter if one is available, even if a `filename` parameter is included first. Previously, the first matching parameter would be used, thereby preventing a more appropriate name from being used. See [bug 588781](https://bugzilla.mozilla.org/show_bug.cgi?id=588781).
-   Firefox 82 (and later) and Chrome prioritize the HTML [&lt;a&gt; element's](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) `download` attribute over the `Content-Disposition` `inline` parameter (for [same-origin URLs](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy)). Earlier Firefox versions prioritize the header and will display the content inline.

See also
--------

-   [HTML Forms](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms)
-   The [`Content-Type`](content-type) defining the boundary of the multipart body.
-   The [`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData) interface used to manipulate form data for use in the [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) API.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Disposition$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Disposition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Disposition</a>
