# CookieStore.set()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `set()` method of the [`CookieStore`](../cookiestore) interface sets a cookie with the given name and value or options object. (See below.)

## Syntax

    var promise = cookieStore.set(name,value);
    var promise = cookieStore.set(options);

### Parameters

This method requires one of the following:

`name`  
A [`USVString`](../usvstring) with the name of the cookie.

`value`  
A [`USVString`](../usvstring) with the value of the cookie.

options  
An object containing:

`name`  
A [`USVString`](../usvstring) with the name of a cookie.

`value`  
A [`USVString`](../usvstring) with the value of the cookie.

`expires`<span class="badge inline optional">Optional</span>  
A [`DOMTimeStamp`](../domtimestamp) containing the expiration date of the cookie.

`domain`<span class="badge inline optional">Optional</span>  
A [`USVString`](../usvstring) containing the domain of the cookie.

`path`<span class="badge inline optional">Optional</span>  
A [`USVString`](../usvstring) containing the path of the cookie.

`sameSite`<span class="badge inline optional">Optional</span>  
One of the following [SameSite](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite) values:

`"strict"`  
Cookies will only be sent in a first-party context and not be sent along with requests initiated by third party websites.

`"lax"`  
Cookies are not sent on normal cross-site subrequests (for example to load images or frames into a third party site), but are sent when a user is navigating to the origin site (i.e. when following a link).

`"none"`  
Cookies will be sent in all contexts.

**Note**
For more information on SameSite cookies see [SameSite cookies explained](https://web.dev/samesite-cookies-explained/).

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`Undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) when setting the cookie completes.

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if setting the cookie with the given values fails.

[`DOMException`](../domexception) `SecurityError`  
Thrown if the origin does not [serialize](https://developer.mozilla.org/en-US/docs/Glossary/Serialization) to a URL.

## Examples

The following example sets a cookie by passing an object with `name`, `value`, `expires`, and `domain`.

    const day = 24 * 60 * 60 * 1000;
    cookieStore.set({
      name: "cookie1",
      value: "cookie1-value",
      expires: Date.now() + day,
      domain: "example.com"
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/">Cookie Store API</a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`set`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CookieStore/set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CookieStore/set</a>
