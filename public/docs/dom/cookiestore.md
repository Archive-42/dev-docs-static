# CookieStore

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `CookieStore` interface of the [`Cookie Store API`](cookie_store_api) provides methods for getting and setting cookies asynchronously from either a page or a service worker.

The `CookieStore` is accessed via attributes in the global scope in a [`Window`](window) or [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) context. Therefore there is no constructor.

## Properties

### Event handlers

[`CookieStore.onChange`](cookiestore/onchange)  
The `onchange` EventHandler is called whenever a cookie is changed.

## Methods

[`CookieStore.delete()`](cookiestore/delete)  
The `delete()` method deletes a cookie with the given name or options object, it returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the deletion completes.

[`CookieStore.get()`](cookiestore/get)  
The `get()` method gets a single cookie with the given name or options object, it returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with details of a single cookie.

[`CookieStore.getAll()`](cookiestore/getall)  
The `getAll()` method gets all matching cookies, it returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a list of cookies.

[`CookieStore.set()`](cookiestore/set)  
The `set()` method sets a cookie with the given name and value or options object, it returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the cookie is set.

## Examples

In this example we set a cookie and write to the console feedback as to whether the operation succeeded or failed.

    const day = 24 * 60 * 60 * 1000;
    cookieStore.set({
      name: "cookie1",
      value: "cookie1-value",
      expires: Date.now() + day,
      domain: "example.com"
    })
    .then(
      function() {
        console.log("It worked!");
      },
      function(reason) {
        console.error("It failed: ", reason);
      }
    );

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

`CookieStore`

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

`onchange`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CookieStore" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CookieStore</a>
