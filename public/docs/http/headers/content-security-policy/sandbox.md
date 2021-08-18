CSP: sandbox
============

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `sandbox` directive enables a sandbox for the requested resource similar to the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) `sandbox` attribute. It applies restrictions to a page's actions including preventing popups, preventing the execution of plugins and scripts, and enforcing a same-origin policy.

CSP version

1.1 / 2

Directive type

[Document directive](https://developer.mozilla.org/en-US/docs/Glossary/Document_directive)

This directive is not supported in the [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element or by the [`Content-Security-policy-Report-Only`](../content-security-policy-report-only) header field.

Syntax
------

    Content-Security-Policy: sandbox;
    Content-Security-Policy: sandbox <value>;

where `<value>` can optionally be one of the following values:

 `allow-downloads-without-user-activation`   
Allows for downloads to occur without a gesture from the user.

<!-- -->

`allow-forms`  
Allows the page to submit forms. If this keyword is not used, this operation is not allowed.

`allow-modals`  
Allows the page to open modal windows.

`allow-orientation-lock`  
Allows the page to disable the ability to lock the screen orientation.

`allow-pointer-lock`  
Allows the page to use the [Pointer Lock API](https://developer.mozilla.org/en-US/docs/WebAPI/Pointer_Lock).

`allow-popups`  
Allows popups (like from `window.open`, `target="_blank"`, `showModalDialog`). If this keyword is not used, that functionality will silently fail.

`allow-popups-to-escape-sandbox`  
Allows a sandboxed document to open new windows without forcing the sandboxing flags upon them. This will allow, for example, a third-party advertisement to be safely sandboxed without forcing the same restrictions upon a landing page.

`allow-presentation`  
Allows embedders to have control over whether an iframe can start a presentation session.

`allow-same-origin`  
Allows the content to be treated as being from its normal origin. If this keyword is not used, the embedded content is treated as being from a unique origin.

`allow-scripts`  
Allows the page to run scripts (but not create pop-up windows). If this keyword is not used, this operation is not allowed.

 `allow-storage-access-by-user-activation`   
Lets the resource request access to the parent's storage capabilities with the [Storage Access API](https://developer.mozilla.org/en-US/docs/Web/API/Storage_Access_API).

`allow-top-navigation`  
Allows the page to navigate (load) content to the top-level browsing context. If this keyword is not used, this operation is not allowed.

`allow-top-navigation-by-user-activation`  
Lets the resource navigate the top-level browsing context, but only if initiated by a user gesture.

Examples
--------

    Content-Security-Policy: sandbox allow-scripts;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#directive-sandbox">Content Security Policy Level 3<br />
<span class="small">The definition of 'sandbox' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-csp/2/#directive-sandbox">Content Security Policy Level 2<br />
<span class="small">The definition of 'sandbox' in that specification.</span></a></td><td><span class="spec-REC">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`sandbox`

25

14

50

10

15

7

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`sandbox`

Yes

Yes

50

?

7

Yes

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   `sandbox` attribute on [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) elements

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/sandbox$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/sandbox" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/sandbox</a>
