# CookieStore.getAll()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `getAll()` method of the [`CookieStore`](../cookiestore) interface returns a list of cookies that match the name or options passed to it. Passing no parameters will return all cookies for the current context.

## Syntax

    var list = cookieStore.getAll(name);
    var list = cookieStore.getAll(options);

### Parameters

`name`<span class="badge inline optional">Optional</span>  
A [`USVString`](../usvstring) with the name of a cookie.

`options`<span class="badge inline optional">Optional</span>  
An object containing:

`name`  
A [`USVString`](../usvstring) with the name of a cookie.

`url`  
A [`USVString`](../usvstring) with the url of a cookie.

### Note:

The `url` option enables the modification of a cookie scoped under a particular URL. Service workers can obtain cookies that would be sent to any URL under their scope. From a document you may only obtain the cookies at the current URL, so the only valid URL in a document context is the document's URL.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a list of cookies for the given name or options.

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if getting the cookie or cookies represented by the given `name` or `options` fails.

## Examples

In this example we use `getAll()` with no parameters. This returns all of the cookies for this context as an array of objects.

    let cookies = cookieStore.getAll();
    if (cookies) {
      console.log(cookies);
    } else {
      console.log('Cookie not found');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/#CookieStore-getAll">Cookie Store API<br />
<span class="small">The definition of 'CookieStore.getAll()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getAll`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CookieStore/getAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CookieStore/getAll</a>
