# ExtendableCookieChangeEvent.changed

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `changed` read-only property of the [`ExtendableCookieChangeEvent`](../extendablecookiechangeevent) interface returns any cookies that have been changed by the given `ExtendableCookieChangeEvent` instance.

## Syntax

    var array = ExtendableCookieChangeEvent.changed;

### Value

An array of objects containing the changed cookie(s). Each object contains the following properties:

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
A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the cookie is from a site with a secure context (HTTPS rather than HTTP).

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

## Examples

In this example when the cookie is set, the event listener logs the `changed` property to the console. The first item in that array contains an object representing the cookie that has just been set.

    self.addEventListener('cookiechange', (event) => {
      console.log(event.changed[0]);
    });

    const one_day = 24 * 60 * 60 * 1000;
    cookieStore.set({
      name: "cookie1",
      value: "cookie1-value",
      expires: Date.now() + one_day,
      domain: "example.com"
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/#dom-extendablecookiechangeevent-changed">Cookie Store API<br />
<span class="small">The definition of 'ExtendableCookieChangeEvent.changed' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`changed`

87

87

No

No

73

No

No

87

No

62

No

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ExtendableCookieChangeEvent/changed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ExtendableCookieChangeEvent/changed</a>
