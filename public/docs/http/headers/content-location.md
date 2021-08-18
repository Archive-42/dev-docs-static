Content-Location
================

The `Content-Location` header indicates an alternate location for the returned data. The principal use is to indicate the URL of a resource transmitted as the result of [content negotiation](../content_negotiation).

[`Location`](location) and `Content-Location` are different. `Location` indicates the URL of a redirect, while `Content-Location` indicates the direct URL to use to access the resource, without further content negotiation in the future. `Location` is a header associated with the response, while `Content-Location` is associated with the data returned. This distinction may seem abstract without [examples](#Examples).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Entity_header">Entity header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Content-Location: <url>

Directives
----------

&lt;url&gt;  
A [relative](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL#Examples_of_relative_URLs) (to the request URL) or [absolute](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL#Examples_of_absolute_URLs) URL.

Examples
--------

### Requesting data from a server in different formats

Let's say a site's API can return data in [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON), [XML](https://developer.mozilla.org/en-US/docs/Glossary/XML), or [CSV](https://en.wikipedia.org/wiki/Comma-separated_values) formats. If the URL for a particular document is at `https://example.com/documents/foo`, the site could return different URLs for `Content-Location` depending on the request's [`Accept`](accept) header:

<table><thead><tr class="header"><th>Request header</th><th>Response header</th></tr></thead><tbody><tr class="odd"><td><code>Accept: application/json, text/json</code></td><td><code>Content-Location: /documents/foo.json</code></td></tr><tr class="even"><td><code>Accept: application/xml, text/xml</code></td><td><code>Content-Location: /documents/foo.xml</code></td></tr><tr class="odd"><td><code>Accept: text/plain, text/*</code></td><td><code>Content-Location: /documents/foo.txt</code></td></tr></tbody></table>

These URLs are examples — the site could serve the different filetypes with any URL patterns it wishes, such as a [query string parameter](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHyperlinkElementUtils/search): `/documents/foo?format=json`, `/documents/foo?format=xml`, and so on.

Then the client could remember that the JSON version is available at that particular URL, skipping content negotation the next time it requests that document.

The server could also consider other [content negotiation](../content_negotiation) headers, such as [`Accept-Language`](accept-language).

### Pointing to a new document (HTTP 201 Created)

Say you're creating a new blog post through a site's API:

    PUT /new/post
    Host: example.com
    Content-Type: text/markdown

    # My first blog post!

    I made this through `example.com`'s API. I hope it worked.

The site returns a generic success message confirming the post was published. The server specifies *where* the new post is with `Content-Location`:

    HTTP/1.1 201 Created
    Content-Type: text/plain; charset=utf-8
    Content-Location: /my-first-blog-post

    ✅ Success!

### Indicating the URL of a transaction's result

Say you have a `<form>` for sending money to another user of a site.

    <form action="/send-payment" method="post">
      <p>
        <label>Who do you want to send the money to?
          <input type="text" name="recipient">
        </label>
      </p>

      <p>
        <label>How much?
          <input type="number" name="amount">
        </label>
      </p>

      <button type="submit">Send Money</button>
    </form>

When the form is submitted, the site generates a receipt for the transaction. The server could use `Content-Location` to indicate that receipt's URL for future access.

    HTTP/1.1 200 OK
    Content-Type: text/html; charset=utf-8
    Content-Location: /my-receipts/38

    <!doctype html>
    (Lots of HTML…)

    <p>You sent $38.00 to ExampleUser.</p>

    (Lots more HTML…)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-3.1.4.2">RFC 7231, section 3.1.4.2: Content-Location</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Content-Location`

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

`Content-Location`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Location`](location)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Location$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Location" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Location</a>
