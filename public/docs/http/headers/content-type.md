Content-Type
============

The `Content-Type` entity header is used to indicate the [media type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) of the resource.

In responses, a `Content-Type` header tells the client what the content type of the returned content actually is. Browsers will do MIME sniffing in some cases and will not necessarily follow the value of this header; to prevent this behavior, the header [`X-Content-Type-Options`](x-content-type-options) can be set to `nosniff`.

In requests, (such as [`POST`](../methods/post) or [`PUT`](../methods/put)), the client tells the server what type of data is actually sent.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Entity_header">Entity header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_response_header">CORS-safelisted response header</a></td><td>yes</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header">CORS-safelisted request header</a></td><td>yes, with the additional restriction that values can't contain a <em>CORS-unsafe request header byte</em>: 0x00-0x1F (except 0x09 (HT)), <code>"():&lt;&gt;?@[\]{}</code>, and 0x7F (DEL).<br />
It also needs to have a MIME type of its parsed value (ignoring parameters) of either <code>application/x-www-form-urlencoded</code>, <code>multipart/form-data</code>, or <code>text/plain</code>.</td></tr></tbody></table>

Syntax
------

    Content-Type: text/html; charset=UTF-8
    Content-Type: multipart/form-data; boundary=something

Directives
----------

`media-type`  
The [MIME type](../basics_of_http/mime_types) of the resource or the data.

charset  
The character encoding standard.

boundary  
For multipart entities the `boundary` directive is required, which consists of 1 to 70 characters from a set of characters known to be very robust through email gateways, and not ending with white space. It is used to encapsulate the boundaries of the multiple parts of the message. Often, the header boundary is prepended with two dashes and the final boundary has two dashes appended at the end.

Examples
--------

### `Content-Type` in HTML forms

In a [`POST`](../methods/post) request, resulting from an HTML form submission, the `Content-Type` of the request is specified by the `enctype` attribute on the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element.

    <form action="/" method="post" enctype="multipart/form-data">
      <input type="text" name="description" value="some text">
      <input type="file" name="myFile">
      <button type="submit">Submit</button>
    </form>

The request looks something like this (less interesting headers are omitted here):

    POST /foo HTTP/1.1
    Content-Length: 68137
    Content-Type: multipart/form-data; boundary=---------------------------974767299852498929531610575

    -----------------------------974767299852498929531610575
    Content-Disposition: form-data; name="description" 

    some text
    -----------------------------974767299852498929531610575
    Content-Disposition: form-data; name="myFile"; filename="foo.txt" 
    Content-Type: text/plain 

    (content of the uploaded file foo.txt)
    -----------------------------974767299852498929531610575--

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7233#section-4.1">RFC 7233, section 4.1: Content-Type in multipart</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Range Requests</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc7231#section-3.1.1.5">RFC 7231, section 3.1.1.5: Content-Type</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Content-Type`

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

`Content-Type`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Accept`](accept) and [`Accept-Charset`](accept-charset)
-   [`Content-Disposition`](content-disposition)
-   [`206`](../status/206) Partial Content
-   [`X-Content-Type-Options`](x-content-type-options)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type</a>
