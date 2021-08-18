CSP: require-trusted-types-for
==============================

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `require-trusted-types-for` directive instructs user agents to control the data passed to DOM XSS sink functions, like [Element.innerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML) setter.

When used, those functions only accept non-spoofable, typed values created by Trusted Type policies, and reject strings. Together with `trusted-types` directive, which guards creation of Trusted Type policies, this allows authors to define rules guarding writing values to the DOM and thus reducing the DOM XSS attack surface to small, isolated parts of the web application codebase, facilitating their monitoring and code review.

Syntax
------

    Content-Security-Policy: require-trusted-types-for 'script';

`'script'`  
Disallows using strings with DOM XSS injection sink functions, and requires matching types created by Trusted Type policies.

Examples
--------

    // Content-Security-Policy: require-trusted-types-for 'script'; trusted-types foo;

    const attackerInput = '<svg onload="alert(/cross-site-scripting/)" />';
    const el = document.createElement('div');

    if (typeof trustedTypes !== 'undefined') {
      // Create a policy that can create TrustedHTML values 
      // after sanitizing the input strings with DOMPurify library.
      const sanitizer = trustedTypes.createPolicy('foo', {
        createHTML: (input) => DOMPurify.sanitize(input)
      });

      el.innerHTML = sanitizer.createHTML(attackerInput);  // Puts the sanitized value into the DOM.
      el.innerHTML = attackerInput;                        // Rejects a string value; throws a TypeError.
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

[`trusted-types`](trusted-types)

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

[`trusted-types`](trusted-types)

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
-   [DOM XSS injection sinks covered by Trusted Types](https://w3c.github.io/webappsec-trusted-types/dist/spec/#injection-sinks)
-   [Prevent DOM-based cross-site scripting vulnerabilities with Trusted Types](https://web.dev/trusted-types)
-   Trusted Types with [DOMPurify](https://github.com/cure53/DOMPurify#what-about-dompurify-and-trusted-types) XSS sanitizer

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/require-trusted-types-for$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/require-trusted-types-for" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/require-trusted-types-for</a>
