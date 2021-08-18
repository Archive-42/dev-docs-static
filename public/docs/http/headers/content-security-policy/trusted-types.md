CSP: trusted-types
==================

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `trusted-types` directive instructs user agents to restrict the creation of Trusted Types policies - functions that build non-spoofable, typed values intended to be passed to DOM XSS sinks in place of strings.

Together with `require-trusted-types-for` directive, this allows authors to define rules guarding writing values to the DOM and thus reducing the DOM XSS attack surface to small, isolated parts of the web application codebase, facilitating their monitoring and code review. This directive declares an allow-list of trusted type policy names created with `TrustedTypes.createPolicy` from Trusted Types API.

Syntax
------

    Content-Security-Policy: trusted-types;
    Content-Security-Policy: trusted-types 'none';
    Content-Security-Policy: trusted-types <policyName>;
    Content-Security-Policy: trusted-types <policyName> <policyName> 'allow-duplicates'; 

&lt;policyName&gt;  
A valid policy name consists only of alphanumeric characters, or one of "`-#=_/@.%`". A star (`*`) as a policy name instructs the user agent to allow any unique policy name ('`allow-duplicates`' may relax that further).

`'none'`  
Disallows creating any Trusted Type policy (same as not specifying any *&lt;policyName&gt;*).

`'allow-duplicates'`  
Allows for creating policies with a name that was already used.

Examples
--------

    // Content-Security-Policy: trusted-types foo bar 'allow-duplicates';

    if (typeof trustedTypes !== 'undefined') {
      const policyFoo = trustedTypes.createPolicy('foo', {});
      const policyFoo2 = trustedTypes.createPolicy('foo', {});
      const policyBaz = trustedTypes.createPolicy('baz', {}); // Throws and dispatches a SecurityPolicyViolationEvent.
    }

Polyfill
--------

A [polyfill for Trusted Types](https://github.com/w3c/webappsec-trusted-types#polyfill) is available on Github.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/">Trusted Types</a></td><td>Draft</td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`trusted-types`

83

83

73 — 76

Disabled

Disabled From version 73 until version 76 (exclusive): this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

?

No

No

No

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`trusted-types`

83

83

83

73 — 76

Disabled

Disabled From version 73 until version 76 (exclusive): this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

No

No

No

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [Cross-Site Scripting (XSS)](https://developer.mozilla.org/en-US/docs/Glossary/Cross-site_scripting)
-   [Prevent DOM-based cross-site scripting vulnerabilities with Trusted Types](https://web.dev/trusted-types)
-   Trusted Types with [DOMPurify](https://github.com/cure53/DOMPurify#what-about-dompurify-and-trusted-types) XSS sanitizer

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/trusted-types$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/trusted-types" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/trusted-types</a>
