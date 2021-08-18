POST
====

The `POST` sends data to the server. The type of the body of the request is indicated by the [`Content-Type`](../headers/content-type) header.

The difference between [`PUT`](put) and `POST` is that `PUT` is idempotent: calling it once or several times successively has the same effect (that is no *side* effect), where successive identical `POST` may have additional effects, like passing an order several times.

A `POST` request is typically sent via an [HTML form](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms) and results in a change on the server. In this case, the content type is selected by putting the adequate string in the `enctype` attribute of the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element or the `formenctype` attribute of the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) or [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) elements:

-   `application/x-www-form-urlencoded`: the keys and values are encoded in key-value tuples separated by `'&'`, with a `'='` between the key and the value. Non-alphanumeric characters in both keys and values are [percent encoded](https://developer.mozilla.org/en-US/docs/Glossary/percent-encoding): this is the reason why this type is not suitable to use with binary data (use `multipart/form-data` instead)
-   `multipart/form-data`: each value is sent as a block of data ("body part"), with a user agent-defined delimiter ("boundary") separating each part. The keys are given in the `Content-Disposition` header of each part.
-   `text/plain`

When the `POST` request is sent via a method other than an HTML form — like via an [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) — the body can take any type. As described in the HTTP 1.1 specification, `POST` is designed to allow a uniform method to cover the following functions:

-   Annotation of existing resources
-   Posting a message to a bulletin board, newsgroup, mailing list, or similar group of articles;
-   Adding a new user through a signup modal;
-   Providing a block of data, such as the result of submitting a form, to a data-handling process;
-   Extending a database through an append operation.

<table><tbody><tr class="odd"><td>Request has body</td><td>Yes</td></tr><tr class="even"><td>Successful response has body</td><td>Yes</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Safe">Safe</a></td><td>No</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Idempotent">Idempotent</a></td><td>No</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Cacheable">Cacheable</a></td><td>Only if freshness information is included</td></tr><tr class="even"><td>Allowed in <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms">HTML forms</a></td><td>Yes</td></tr></tbody></table>

Syntax
------

    POST /test

Example
-------

A simple form using the default `application/x-www-form-urlencoded` content type:

    POST /test HTTP/1.1
    Host: foo.example
    Content-Type: application/x-www-form-urlencoded
    Content-Length: 27

    field1=value1&field2=value2

A form using the `multipart/form-data` content type:

    POST /test HTTP/1.1 
    Host: foo.example
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

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-4.3.3">RFC 7231, section 4.3.3: POST</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc2046#section-5.1.1">RFC 2046, section 5.1.1: Common Syntax</a></td><td>Multipurpose Internet Mail Extensions (MIME) Part Two: Media Types</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`POST`

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

`POST`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Content-Type`](../headers/content-type)
-   [`Content-Disposition`](../headers/content-disposition)
-   [`GET`](get)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST</a>
