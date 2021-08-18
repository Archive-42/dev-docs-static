X-DNS-Prefetch-Control
======================

The `X-DNS-Prefetch-Control` HTTP response header controls DNS prefetching, a feature by which browsers proactively perform domain name resolution on both links that the user may choose to follow as well as URLs for items referenced by the document, including images, CSS, JavaScript, and so forth.

This prefetching is performed in the background, so that the [DNS](https://developer.mozilla.org/en-US/docs/Glossary/DNS) is likely to have been resolved by the time the referenced items are needed. This reduces latency when the user clicks a link.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    X-DNS-Prefetch-Control: on
    X-DNS-Prefetch-Control: off

### Directives

on  
Enables DNS prefetching. This is what browsers do, if they support the feature, when this header is not present

off  
Disables DNS prefetching. This is useful if you don't control the link on the pages, or know that you don't want to leak information to these domains.

Description
-----------

DNS requests are very small in terms of bandwidth, but latency can be quite high, especially on mobile networks. By speculatively prefetching DNS results, latency can be reduced significantly at certain times, such as when the user clicks the link. In some cases, latency can be reduced by a second.

The implementation of this prefetching in some browsers allows domain name resolution to occur in parallel with (instead of in serial with) the fetching of actual page content. By doing this, the high-latency domain name resolution process doesn't cause any delay while fetching content.

Page load times – especially on mobile networks – can be measurably improved in this way. If the domain names for images can be resolved in advance of the images being requested, pages that load many images can see an improvement of 5% or more in the time of loading images.

### Configuring prefetching in the browser

In general, you don't need to do anything to manage prefetching. However, the user may wish to disable prefetching. On Firefox, this can be done by setting the `network.dns.disablePrefetch` preference to `true`.

Also, by default, prefetching of embedded link hostnames is not performed on documents loaded over [HTTPS](https://developer.mozilla.org/en-US/docs/Glossary/HTTPS). On Firefox, this can be changed by setting the `network.dns.disablePrefetchFromHTTPS` preference to `false`.

Examples
--------

### Turning on and off prefetching

You can either send the `X-DNS-Prefetch-Control` header server-side, or from individual documents, using the `http-equiv` attribute on the [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element, like this:

    <meta http-equiv="x-dns-prefetch-control" content="off">

You can reverse this setting by setting `content` to "`on`".

### Forcing lookup of specific hostnames

You can force the lookup of specific hostnames without providing specific anchors using that hostname by using the `rel` attribute on the [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) element with a [link type](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types) of `dns-prefetch`:

    <link rel="dns-prefetch" href="https://www.mozilla.org/contribute/">

In this example, the domain name "[www.mozilla.org/contribute](https://www.mozilla.org/contribute/)" will be pre-resolved.

Similarly, the link element can be used to resolve hostnames without providing a complete URL, but only, by preceding the hostname with two slashes:

    <link rel="dns-prefetch" href="//www.mozilla.org/contribute/">

Forced prefetching of hostnames might be useful, for example, on the homepage of a site to force pre-resolution of domain names that are referenced frequently throughout the site even though they are not used on the home page itself. This will improve the overall performance of site even though the performance of the home page may not be affected.

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`X-DNS-Prefetch-Control`

1

≤79

2

?

Yes

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`X-DNS-Prefetch-Control`

Yes

18

4

Yes

?

Yes

See also
--------

-   [DNS Prefetching for Firefox (blog post)](https://bitsup.blogspot.com/2008/11/dns-prefetching-for-firefox.html)
-   [Google Chrome handles DNS prefetching control](https://dev.chromium.org/developers/design-documents/dns-prefetching)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-DNS-Prefetch-Control$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-DNS-Prefetch-Control" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-DNS-Prefetch-Control</a>
