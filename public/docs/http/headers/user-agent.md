User-Agent
==========

The **User-Agent** [request header](https://developer.mozilla.org/en-US/docs/Glossary/request_header) is a characteristic string that lets servers and network peers identify the application, operating system, vendor, and/or version of the requesting [user agent](https://developer.mozilla.org/en-US/docs/Glossary/user_agent).

Please read [Browser detection using the user agent](../browser_detection_using_the_user_agent) for why serving different Web pages or services to different browsers is usually a bad idea.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    User-Agent: <product> / <product-version> <comment>

Common format for web browsers:

    User-Agent: Mozilla/5.0 (<system-information>) <platform> (<platform-details>) <extensions>

### Directives

`<product>`  
A product identifier — its name or development codename.

`<product-version>`  
Version number of the product.

`<comment>`  
Zero or more comments containing more details; sub-product information, for example.

Firefox UA string
-----------------

For more on Firefox- and Gecko-based user agent strings, see the [Firefox user agent string reference](user-agent/firefox). The UA string of Firefox is broken down into 4 components:

    Mozilla/5.0 (platform; rv:geckoversion) Gecko/geckotrail Firefox/firefoxversion

1.  `Mozilla/5.0` is the general token that says the browser is Mozilla-compatible. For historical reasons, almost every browser today sends it.
2.  ***platform*** describes the native platform the browser is running on (Windows, Mac, Linux, Android, etc.), and if it's a mobile phone. [Firefox OS](https://developer.mozilla.org/en-US/docs/Glossary/Firefox_OS) phones simply say `Mobile` — the web is the platform. Note that ***platform*** can consist of multiple "`; `"-separated tokens. See below for further details and examples.
3.  **rv:*geckoversion*** indicates the release version of Gecko (such as "*17.0*"). In recent browsers, ***geckoversion*** is the same as ***firefoxversion***.
4.  ***Gecko/geckotrail*** indicates that the browser is based on [Gecko](https://developer.mozilla.org/en-US/docs/Mozilla/Gecko). (On Desktop, ***geckotrail*** is always the fixed string `20100101`.)
5.  ***Firefox/firefoxversion*** indicates the browser is Firefox, and provides the version (such as "*17.0"*).

### Examples

    Mozilla/5.0 (Windows NT 6.1; Win64; x64; rv:47.0) Gecko/20100101 Firefox/47.0
    Mozilla/5.0 (Macintosh; Intel Mac OS X x.y; rv:42.0) Gecko/20100101 Firefox/42.0

Chrome UA string
----------------

The Chrome (or Chromium/Blink-based engines) user agent string is similar to Firefox’s. For compatibility, it adds strings like `KHTML, like Gecko` and `Safari`.

### Examples

    Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.103 Safari/537.36

Opera UA string
---------------

The Opera browser is also based on the Blink engine, which is why it almost looks the same, but adds `"OPR/<version>"`.

### Examples

    Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.106 Safari/537.36 OPR/38.0.2220.41

Older, Presto-based Opera releases used:

    Opera/9.80 (Macintosh; Intel Mac OS X; U; en) Presto/2.2.15 Version/10.00
    Opera/9.60 (Windows NT 6.0; U; en) Presto/2.1.1

Safari UA string
----------------

In this example, the user agent string is mobile Safari’s version. It contains the word `"Mobile"`.

### Examples

    Mozilla/5.0 (iPhone; CPU iPhone OS 13_5_1 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/13.1.1 Mobile/15E148 Safari/604.1

Internet Explorer UA string
---------------------------

### Examples

    Mozilla/5.0 (compatible; MSIE 9.0; Windows Phone OS 7.5; Trident/5.0; IEMobile/9.0)

Crawler and bot UA strings
--------------------------

### Examples

    Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)

    Mozilla/5.0 (compatible; YandexAccessibilityBot/3.0; +http://yandex.com/bots)

Library and net tool UA strings
-------------------------------

### Examples

    curl/7.64.1

    PostmanRuntime/7.26.5

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-5.5.3">RFC 7231, section 5.5.3: User-Agent</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc2616#section-14.43">RFC 2616, section 14.43: User-Agent</a></td><td>Hypertext Transfer Protocol -- HTTP/1.1</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`User-Agent`

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

`User-Agent`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [User-Agent detection, history and checklist](https://hacks.mozilla.org/2013/09/user-agent-detection-history-and-checklist/)
-   [Firefox user agent string reference](user-agent/firefox)
-   [Browser detection using the user agent](../browser_detection_using_the_user_agent)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent</a>
