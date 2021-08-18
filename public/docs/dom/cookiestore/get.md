# CookieStore.get()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `get()` method of the [`CookieStore`](../cookiestore) interface returns a single cookie with the given name or options object. (See below.) The method will return the first matching cookie for the passed parameters.

## Syntax

    var cookie = CookieStore.get(name);
    var cookie = CookieStore.get(options);

### Parameters

This method requires one of the following:

`name`  
A [`USVString`](../usvstring) with the name of a cookie.

options  
An object containing:

`name`  
A [`USVString`](../usvstring) with the name of a cookie.

`url`  
A [`USVString`](../usvstring) with the url of a cookie.

### Note:

The `url` option enables the modification of a cookie scoped under a particular URL. Service workers can obtain cookies that would be sent to any URL under their scope. From a document you may only obtain the cookies at the current URL, so the only valid URL in a document context is the document's URL.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an object containing the first cookie matching the submitted name or options. This object contains the following properties:

`name`  
A [`USVString`](../usvstring) containing the name of the cookie.

`value`  
A [`USVString`](../usvstring) containing the value of the cookie.

`domain`  
A [`USVString`](../usvstring) containing the domain of the cookie.

`path`  
A [`USVString`](../usvstring) containing the path of the cookie.

`expires`  
A [`DOMTimeStamp`](../domtimestamp) containing the expiration date of the cookie.

`secure`  
A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the cookie is to be used in secure contexts only.

`sameSite`  
One of the following [SameSite](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite) values:

`"strict"`  
Cookies will only be sent in a first-party context and not be sent with requests initiated by third party websites.

`"lax"`  
Cookies are not sent on normal cross-site subrequests (for example to load images or frames into a third party site), but are sent when a user is navigating within the origin site (i.e. when following a link).

`"none"`  
Cookies will be sent in all contexts.

**Note**
For more information on SameSite cookies see [SameSite cookies explained](https://web.dev/samesite-cookies-explained/).

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if getting the cookie represented by the given `name` or `options` fails.

## Examples

In this example we return a cookie named "cookie1". If the cookie is found the result of the Promise is an object containing the details of a single cookie.

    let cookie = cookieStore.get('cookie1');
    if (cookie) {
        console.log(cookie);
    } else {
        console.log('Cookie not found');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/#CookieStore-get">Cookie Store API<br />
<span class="small">The definition of 'CookieStore.get()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`get`

87

87

No

No

73

No

87

87

No

62

No

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CookieStore/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CookieStore/get</a>
