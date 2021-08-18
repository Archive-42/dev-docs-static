&lt;portal&gt;: The Portal element
==================================

The `<portal>` enables the embedding of another HTML page into the current one for the purposes of allowing smoother navigation into new pages.

A `<portal>` is similar to an `<iframe>`. An `<iframe>` allows a separate [browsing context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context) to be embedded. However, the embedded content of a `<portal>` is more limited than that of an `<iframe>`. It cannot be interacted with, and therefore is not suitable for embedding widgets into a document. Instead, the `<portal>` acts as a preview of the content of another page. It can be navigated into therefore allowing for seamless transition to the embedded content.

<table><tbody><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role">button</a></td></tr><tr class="even"><td>DOM interface</td><td><span class="page-not-created"><code>HTMLPortalElement</code></span></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`referrerpolicy`  
Sets the [referrer policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy) to use when requesting the page at the URL given as the value of the `src` attribute.

`src`  
The URL of the page to embed.

Examples
--------

### Basic example

The following example will embed the contents of `https://example.com` as a preview.

    <portal id="exampleportal" src="https://example.com/"></portal>

Accessibility concerns
----------------------

The preview displayed by a `<portal>` is not interactive, therefore does not receive input events or focus. Therefore the embedded contents of the portal are not exposed as elements in the [accessibility tree](https://developer.mozilla.org/en-US/docs/Glossary/Accessibility_tree). The portal can be navigated to and activated like a button, the default behavior when clicking on the portal is to activate it.

Portals are given a default label which is the title of the embedded page. If no title is present the visible text in the preview is concatenated to create a label. The [`aria-label`](../global_attributes#attr-aria-label) attribute can be used to override this.

Portals used for prerendering only should be hidden with the hidden HTML attribute or the CSS [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property with a value of `none`.

When using animations during portal activation the [`prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) [media feature](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries#media_features) should be respected.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/portals/">Portals</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `html.elements.portal`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/portal" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/portal</a>
