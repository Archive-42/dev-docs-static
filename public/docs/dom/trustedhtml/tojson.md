TrustedHTML.toJSON()
====================

The `toJSON()` method of the [`TrustedHTML`](../trustedhtml) interface returns a JSON representation of the stored data.

Syntax
------

    var json = TrustedHTML.toJSON();

### Return value

A [`string`](../domstring) containing a JSON representation of the stored data.

Examples
--------

The constant `escaped` is an object created via the Trusted Types policy escapeHTMLPolicy. The `toString()` method returns a string to safely insert into a document.

    const escapeHTMLPolicy = trustedTypes.createPolicy("myEscapePolicy", {
      createHTML: (string) => string.replace(/\>/g, "<")
    });

    const escaped = escapeHTMLPolicy.createHTML("<img src=x onerror=alert(1)>");
    console.log(escaped.toJSON());

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedhtml-tojson">Trusted Types<br />
<span class="small">The definition of 'TrustedHTML.toJSON()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.TrustedHTML.toJSON`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedHTML/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedHTML/toJSON</a>
