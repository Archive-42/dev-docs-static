SecurityPolicyViolationEvent
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SecurityPolicyViolationEvent` interface inherits from [`Event`](event), and represents the event object of an event sent on a document or worker when its content security policy is violated.

Constructor
-----------

[`SecurityPolicyViolationEvent()`](securitypolicyviolationevent/securitypolicyviolationevent)  
Creates a new `SecurityPolicyViolationEvent` object instance.

Properties
----------

 [`SecurityPolicyViolationEvent.blockedURI`](securitypolicyviolationevent/blockeduri)<span class="badge inline readonly">Read only </span>   
A [`USVString`](usvstring) representing the URI of the resource that was blocked because it violates a policy.

 [`SecurityPolicyViolationEvent.columnNumber`](securitypolicyviolationevent/columnnumber)<span class="badge inline readonly">Read only </span>   
The column number in the document or worker at which the violation occurred.

 [`SecurityPolicyViolationEvent.disposition`](securitypolicyviolationevent/disposition)<span class="badge inline readonly">Read only </span>   
Indicates how the violated policy is configured to be treated by the user agent. This will be `"enforce"` or `"report"`.

 [`SecurityPolicyViolationEvent.documentURI`](securitypolicyviolationevent/documenturi)<span class="badge inline readonly">Read only </span>   
A [`USVString`](usvstring) representing the URI of the document or worker in which the violation was found.

 [`SecurityPolicyViolationEvent.effectiveDirective`](securitypolicyviolationevent/effectivedirective)<span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) representing the directive whose enforcement uncovered the violation.

 [`SecurityPolicyViolationEvent.lineNumber`](securitypolicyviolationevent/linenumber)<span class="badge inline readonly">Read only </span>   
The line number in the document or worker at which the violation occurred.

 [`SecurityPolicyViolationEvent.originalPolicy`](securitypolicyviolationevent/originalpolicy)<span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) containing the policy whose enforcement uncovered the violation.

 [`SecurityPolicyViolationEvent.referrer`](securitypolicyviolationevent/referrer)<span class="badge inline readonly">Read only </span>   
A [`USVString`](usvstring) representing the referrer of the resources whose policy was violated. This will be a URL or `null`.

 [`SecurityPolicyViolationEvent.sample`](securitypolicyviolationevent/sample)<span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) representing a sample of the resource that caused the violation, usually the first 40 characters. This will only be populated if the resource is an inline script, event handler, or style — external resources causing a violation will not generate a sample.

 [`SecurityPolicyViolationEvent.sourceFile`](securitypolicyviolationevent/sourcefile)<span class="badge inline readonly">Read only </span>   
A [`USVString`](usvstring) representing the URI of the document or worker in which the violation was found.

 [`SecurityPolicyViolationEvent.statusCode`](securitypolicyviolationevent/statuscode)<span class="badge inline readonly">Read only </span>   
A number representing the HTTP status code of the document or worker in which the violation occurred.

 [`SecurityPolicyViolationEvent.violatedDirective`](securitypolicyviolationevent/violateddirective)<span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) representing the directive whose enforcement uncovered the violation.

Examples
--------

    document.addEventListener("securitypolicyviolation", (e) => {
      console.log(e.blockedURI);
      console.log(e.violatedDirective);
      console.log(e.originalPolicy);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSP2/#firing-securitypolicyviolationevent-events">Content Security Policy Level 2<br />
<span class="small">The definition of 'SecurityPolicyViolationEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-csp/#report-violation">Content Security Policy Level 3<br />
<span class="small">The definition of 'SecurityPolicyViolationEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`blockedURI`

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

`documentURI`

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

`effectiveDirective`

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

`lineNumber`

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

`originalPolicy`

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

`referrer`

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

`statusCode`

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

`violatedDirective`

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

`worker_support`

56

≤18

63

No

43

Yes

56

56

63

43

Yes

6.0

See also
--------

-   [Content Security Policy (CSP)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SecurityPolicyViolationEvent</a>
