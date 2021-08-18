SecurityPolicyViolationEvent.sample
===================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `sample` read-only property of the [`SecurityPolicyViolationEvent`](../securitypolicyviolationevent) interface is a [`DOMString`](../domstring) representing a sample of the resource that caused the violation.

Syntax
------

    let sample = violationEventInstance.sample;

### Value

A [`DOMString`](../domstring) containing a sample of the resource that caused the violation, usually the first 40 characters. This will only be populated if the resource is an inline script, event handler, or style — external resources causing a violation will not generate a sample.

Example
-------

    document.addEventListener("securitypolicyviolation", (e) => {
      console.log(e.sample);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#dom-securitypolicyviolationevent-sample">Content Security Policy Level 3<br />
<span class="small">The definition of 'sample' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`sample`

59

≤18

63

No

46

Yes

59

59

63

43

Yes

7.0

See also
--------

-   [Content Security Policy (CSP)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent/sample" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent/sample</a>
