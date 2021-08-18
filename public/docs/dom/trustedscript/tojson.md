TrustedScript.toJSON()
======================

The `toJSON()` method of the [`TrustedScript`](../trustedscript) interface returns a JSON representation of the stored data.

Syntax
------

    var json = TrustedScript.toJSON();

### Return value

A [`string`](../domstring) containing a JSON representation of the stored data.

Examples
--------

The constant `sanitized` is an object created via a Trusted Types policy. The `toString()` method returns a string to safely execute as a script.

    const sanitized = scriptPolicy.createScript("eval('2 + 2')");
      console.log(sanitized.toJSON());

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedscript-tojson">Trusted Types<br />
<span class="small">The definition of 'TrustedScript.toJSON()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.TrustedScript.toJSON`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedScript/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedScript/toJSON</a>
