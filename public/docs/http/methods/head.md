HEAD
====

The `HEAD` requests the [headers](../headers) that would be returned if the `HEAD` request's URL was instead requested with the HTTP [`GET`](get) method. For example, if a URL might produce a large download, a `HEAD` request could read its [`Content-Length`](../headers/content-length) header to check the filesize without actually downloading the file.

A response to a `HEAD` method *should not* have a body. If it has one anyway, that body **must be** ignored: any [entity headers](https://developer.mozilla.org/en-US/docs/Glossary/Entity_header) that might describe the erroneous body are instead assumed to describe the response which a similar `GET` request would have received.

If the response to a `HEAD` request shows that a cached URL response is now outdated, the cached copy is invalidated even if no `GET` request was made.

<table><tbody><tr class="odd"><td>Request has body</td><td>No</td></tr><tr class="even"><td>Successful response has body</td><td>No</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Safe">Safe</a></td><td>Yes</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Idempotent">Idempotent</a></td><td>Yes</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Cacheable">Cacheable</a></td><td>Yes</td></tr><tr class="even"><td>Allowed in <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms">HTML forms</a></td><td>No</td></tr></tbody></table>

Syntax
------

    HEAD /index.html

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-4.3.2">RFC 7231, section 4.3.2: HEAD</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`HEAD`

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

`HEAD`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`GET`](get)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD</a>
