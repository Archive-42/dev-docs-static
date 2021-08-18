SecurityPolicyViolationEvent.SecurityPolicyViolationEvent()
===========================================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SecurityPolicyViolationEvent` constructor creates a new `SecurityPolicyViolationEvent` object instance.

Syntax
------

    let SPVEvt = new SecurityPolicyViolationEvent(type, eventInitDict);

### Properties

type  
A [`DOMString`](../domstring) representing the type of security policy violation that occurred.

eventInitDict <span class="badge inline optional">Optional</span>   
A dictionary object containing information about the properties of the `SecurityPolicyViolationEvent` to be constructed. This can include the following properties, but bear in mind that if you do include an `eventInitDict`, certain properties must be included (marked below with **required**):

-   `blockedURI`: The [`blockedURI`](blockeduri) of the `SecurityPolicyViolationEvent`. If not included, the default value is `""`.
-   `columnNumber`: The [`columnNumber`](columnnumber) of the `SecurityPolicyViolationEvent`. If not included, the default value is `0`.
-   `disposition`: The [`disposition`](disposition) of the `SecurityPolicyViolationEvent` (**required**).
-   `documentURI`: The [`documentURI`](documenturi) of the `SecurityPolicyViolationEvent` (**required**).
-   `effectiveDirective`: The [`effectiveDirective`](effectivedirective) of the `SecurityPolicyViolationEvent` (**required**).
-   `lineNumber`: The [`lineNumber`](linenumber) of the `SecurityPolicyViolationEvent`. If not included, the default value is `0`.
-   `originalPolicy`: The [`originalPolicy`](originalpolicy) of the `SecurityPolicyViolationEvent` (**required**).
-   `referrer`: The [`referrer`](referrer) of the `SecurityPolicyViolationEvent`. If not included, the default value is `""`.
-   `sample`: The [`sample`](sample) of the `SecurityPolicyViolationEvent`. If not included, the default value is `""`.
-   `sourceFile`: The [`sourceFile`](sourcefile) of the `SecurityPolicyViolationEvent`. If not included, the default value is `""`.
-   `statusCode`: The [`statusCode`](statuscode) of the `SecurityPolicyViolationEvent` (**required**).
-   `violatedDirective`: The [`violatedDirective`](violateddirective) of the `SecurityPolicyViolationEvent` (**required**).

### Return value

A `SecurityPolicyViolationEvent` object instance.

Example
-------

    let SPVEvt = new SecurityPolicyViolationEvent('foo', {
      ...
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#dom-securitypolicyviolationevent-securitypolicyviolationevent">Content Security Policy Level 3<br />
<span class="small">The definition of 'SecurityPolicyViolationEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`SecurityPolicyViolationEvent`

Yes

≤18

63

No

Yes

Yes

Yes

Yes

63

Yes

Yes

Yes

See also
--------

-   [Content Security Policy (CSP)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent/SecurityPolicyViolationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent/SecurityPolicyViolationEvent</a>
