# CookieChangeEvent

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `CookieChangeEvent` interface of the [`Cookie Store API`](cookie_store_api) is the event type passed to [`CookieStore.onchange()`](cookiestore/onchange) when any cookie changes have occured. A cookie change consists of a cookie and a type (either "changed" or "deleted").

Cookie changes that will cause the `CookieChangeEvent` to be dispatched are:

- A cookie is newly created and not immediately removed. In this case `type` is "changed".
- A cookie is newly created and immediately removed. In this case `type` is "deleted"
- A cookie is removed. In this case `type` is "deleted".

**Note**

A cookie that is replaced due to the insertion of another cookie with the same name, domain, and path, is ignored and does not trigger a change event.

## Constructor

[`CookieChangeEvent.CookieChangeEvent()`](cookiechangeevent/cookiechangeevent)  
Creates a new `CookieChangeEvent`.

## Properties

_This interface also inherits properties from [`Event`](event)._

[`CookieChangeEvent.changed`](cookiechangeevent/changed)<span class="badge inline readonly">Read only </span>  
Returns an array containing one or more changed cookies.

[`CookieChangeEvent.deleted`](cookiechangeevent/deleted)<span class="badge inline readonly">Read only </span>  
Returns an array containing one or more deleted cookies.

## Examples

In this example when the cookie is set, the event listener logs the event to the console. This is a `CookieChangeEvent` object with the [`changed`](cookiechangeevent/changed) property containing an object representing the cookie that has just been set.

    cookieStore.addEventListener('change', (event) => {
      console.log(event);
    });

    const one_day = 24 * 60 * 60 * 1000;
    cookieStore.set({
      name: "cookie1",
      value: "cookie1-value",
      expires: Date.now() + one_day,
      domain: "example.com"
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/#CookieChangeEvent">Cookie Store API<br />
<span class="small">The definition of 'CookieChangeEvent' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CookieChangeEvent`

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

`CookieChangeEvent`

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

`changed`

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

`deleted`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CookieChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CookieChangeEvent</a>
