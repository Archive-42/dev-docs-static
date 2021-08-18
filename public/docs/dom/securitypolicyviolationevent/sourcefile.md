SecurityPolicyViolationEvent.sourceFile
=======================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `sourceFile` read-only property of the [`SecurityPolicyViolationEvent`](../securitypolicyviolationevent) interface is a [`USVString`](../usvstring) representing the URI of the document or worker in which the violation was found.

Syntax
------

    let source = violationEventInstance.sourceFile;

### Value

A [`USVString`](../usvstring) representing the URI of the document or worker in which the violation was found.

Example
-------

    document.addEventListener("securitypolicyviolation", (e) => {
      console.log(e.sourceFile);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#dom-securitypolicyviolationevent-sourcefile">Content Security Policy Level 3<br />
<span class="small">The definition of 'sourceFile' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`sourceFile`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent/sourceFile" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent/sourceFile</a>
