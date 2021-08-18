# CookieStore.delete()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `delete()` method of the [`CookieStore`](../cookiestore) interface deletes a cookie with the given name or options object. (See below.) The `delete()` method expires the cookie by changing the date to one in the past.

## Syntax

    var promise = cookieStore.delete(name);
    var promise = cookieStore.delete(options);

### Parameters

This method requires one of the following:

`name`  
A [`USVString`](../usvstring) with the name of a cookie.

options  
An object containing:

`name`  
A [`USVString`](../usvstring) with the name of a cookie.

`url`<span class="badge inline optional">Optional</span>  
A [`USVString`](../usvstring) with the url of a cookie.

`path`<span class="badge inline optional">Optional</span>  
A [`USVString`](../usvstring) containing a path.

### Note:

The `url` option enables the modification of a cookie scoped under a particular URL. Service workers can obtain cookies that would be sent to any URL under their scope. From a document you may only obtain the cookies at the current URL, so the only valid URL in a document context is the document's URL.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`Undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) when deletion completes.

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if deleting the cookie represented by the given `name` or `options` fails.

## Examples

In this example a cookie is deleted by passing the name to the `delete()` method.

    let result = cookieStore.delete('cookie1');
    console.log(result);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/#CookieStore-delete">Cookie Store API<br />
<span class="small">The definition of 'CookieStore.delete()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`delete`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CookieStore/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CookieStore/delete</a>
