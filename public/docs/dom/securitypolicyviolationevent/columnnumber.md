SecurityPolicyViolationEvent.columnNumber
=========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `columnNumber` read-only property of the [`SecurityPolicyViolationEvent`](../securitypolicyviolationevent) interface is the column number in the document or worker at which the violation occurred.

Syntax
------

    let colNum = violationEventInstance.columnNumber;

### Value

A number representing the column number where the violation occurred.

Example
-------

    document.addEventListener("securitypolicyviolation", (e) => {
      console.log(e.columnNumber);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#dom-securitypolicyviolationevent-columnnumber">Content Security Policy Level 3<br />
<span class="small">The definition of 'columnNumber' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`columnNumber`

Yes

15

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent/columnNumber" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent/columnNumber</a>
