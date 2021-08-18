ExtendableCookieChangeEvent.ExtendableCookieChangeEvent()
=========================================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `ExtendableCookieChangeEvent()` constructor creates a new [`ExtendableCookieChangeEvent`](../extendablecookiechangeevent) object which is the event type passed to <span class="page-not-created">`ServiceWorkerRegistration.oncookiechange()`</span>. This constructor is called by the browser when a change event occurs.

**Note**

This event constructor is generally not needed for production web sites. It's primary use is for tests that require an instance of this event.

Syntax
------

    var extendableCookieChangeEvent = new ExtendableCookieChangeEvent(type, [eventInitDict]);

### Parameters

`type`  
A [`DOMString`](../domstring) with the value `"changed"` or `"deleted"`.

 `eventInitDict`<span class="badge inline optional">Optional</span>   
An object containing:

`changed`  
An array containing a changed cookie.

`deleted`  
An array containing a deleted cookie.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/#dom-extendablecookiechangeevent-extendablecookiechangeevent">Cookie Store API<br />
<span class="small">The definition of 'ExtendableCookieChangeEvent()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`ExtendableCookieChangeEvent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ExtendableCookieChangeEvent/ExtendableCookieChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ExtendableCookieChangeEvent/ExtendableCookieChangeEvent</a>
