SecurityPolicyViolationEvent.disposition
========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `disposition` read-only property of the [`SecurityPolicyViolationEvent`](../securitypolicyviolationevent) interface indicates how the violated policy is configured to be treated by the user agent.

Syntax
------

    let disposition = violationEventInstance.disposition;

### Value

A value defined in the [SecurityPolicyViolationEventDisposition enum](https://w3c.github.io/webappsec-csp/#enumdef-securitypolicyviolationeventdisposition) representing the URI of the blocked resource. Possible values are `"enforce"` or `"report"`

Example
-------

    document.addEventListener("securitypolicyviolation", (e) => {
      console.log(e.disposition);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#dom-securitypolicyviolationevent-disposition">Content Security Policy Level 3<br />
<span class="small">The definition of 'disposition' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`disposition`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent/disposition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent/disposition</a>
