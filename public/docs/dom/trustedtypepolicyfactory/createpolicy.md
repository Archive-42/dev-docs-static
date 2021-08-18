TrustedTypePolicyFactory.createPolicy()
=======================================

The `createPolicy()` method of the [`TrustedTypePolicyFactory`](../trustedtypepolicyfactory) interface creates a [`TrustedTypePolicy`](../trustedtypepolicy) object that implements the rules passed as `policyOptions`.

### The default policy

In Chrome a policy with a name of "default" creates a special policy that will be used if a string (rather than a Trusted Type object) is passed to an injection sink. This can be used in a transitional phase while moving from an application that inserted strings into injection sinks.

**Note**

The above behavior is not yet settled in the specification and may change in future.

**Note**

A lax default policy could defeat the purpose of using Trusted Types, and therefore should be defined with strict rules to ensure it cannot be used to run dangerous code.

Syntax
------

    var policy = TrustedTypePolicyFactory.createPolicy(policyName,policyOptions);

### Parameters

`policyName`  
A [`DOMString`](../domstring) with the name of the policy.

 `policyOptions`<span class="badge inline optional">Optional</span>   
User-defined functions for converting strings into trusted values.

`CreateHTML(input[,args])`  
A callback function in the form of a [`string`](../domstring) that contains code to run when creating a [`TrustedHTML`](../trustedhtml) object.

`CreateScript(input[,args])`  
A callback function in the form of a [`string`](../domstring) that contains code to run when creating a [`TrustedScript`](../trustedscript) object.

`CreateScriptURL(input[,args])`  
A callback function in the form of a [`string`](../domstring) that contains code to run when creating a [`TrustedScriptURL`](../trustedscripturl) object.

### Return value

A [`TrustedTypePolicy`](../trustedtypepolicy) object.

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if policy names are restricted by the [Content Security Policy `trusted-types` directive](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/trusted-types) and this name is not on the allowlist.

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if the name is a duplicate and the [Content Security Policy trusted-types directive](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/trusted-types) is not using `allow-duplicates`.

Examples
--------

The below code creates a policy with the name `"myEscapePolicy"` with a function defined for `createHTML()` which sanitizes HTML.

    const escapeHTMLPolicy = trustedTypes.createPolicy("myEscapePolicy", {
      createHTML: (string) => string.replace(/\>/g, "<")
    });

### Creating a default policy

On a site where Trusted Types are enforced via a Content Security Policy with the `require-trusted-types-for` directive set to `script`, any injection script that accepts a script expects a Trusted Type object. In the case that a string is inserted instead, the following default policy will be used.

The policy logs a message to the console to remind the developer to refactor this part of the application to use a Trusted Type object. It also appends details of the use of the default policy, type, and injection sink to the returned value.

    trustedTypes.createPolicy('default', {
      createScriptURL: (s, type, sink) => {
        console.log("Please refactor.");
        return s + '?default-policy-used&type=' + encodeURIComponent(type) +
              '&sink=' + encodeURIComponent(sink);
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicyfactory-createpolicy">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicyFactory.createPolicy()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`createPolicy`

83

83

No

No

69

No

83

83

No

59

No

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/createPolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/createPolicy</a>
