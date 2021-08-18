# Document.domain

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `domain` property of the [`Document`](../document) interface gets/sets the domain portion of the [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin) of the current document, as used by the [same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy).

## Syntax

### Getter

    const domainString = document.domain

The getter for this property returns the domain portion of the current document's origin. In most cases, this will be the hostname portion of the document's URL. However, there are some exceptions:

- If the page has an opaque [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin), e.g. for a page with a [data URL](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs), then it will return the empty string.
- If the `document.domain` [setter](#setter) has been used, then it will return the value that was set.

Usually it is better to use the [`Location.hostname`](../location/hostname) property instead.

### Setter

    document.domain = domainString

The setter for this property can be used to _change_ a page's [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin), and thus modify how certain security checks are performed. It can only be set to the same or a parent domain. For example, if `https://a.example.com` and `https://b.example.com` both use

    document.domain = "example.com";

then they have both modified their origin to have the same domain, and they can now access each other's DOM directly—despite being cross-origin, which would normally prevent such access.

Note that setting `document.domain` to its current value is not a no-op. It still changes the origin. For example, if one page sets

    document.domain = document.domain;

then it will be counted as cross-origin from any other normally-same-origin pages that have not done the same thing.

#### Deprecation

The `document.domain` setter is deprecated. It undermines the security protections provided by the [same origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy), and complicates the origin model in browsers, leading to interoperability problems and security bugs.

Attempting to set `document.domain` is dangerous. It opens up full access to a page's DOM from _all_ subdomains, which is likely not be what is intended. It also removes the port component from the origin, so now your page can be accessed by other pages with the same IP address or same host component, even on a different port.

This is especially insecure on shared hosting. For example, another shared hosting customer is able to host a site at the same IP address but on a different port, then setting `document.domain` will remove the same-origin protection that normally protects you from that other customer's site accessing your site's data.

Similar problems occur with shared hosting sites that give each customer a different subdomain. If a site sets `document.domain`, any other customer on a different subdomain can now do the same thing, and start accessing the data of the original site.

Instead of using `document.domain` to facilitate cross-origin communication, you should use [`Window.postMessage`](../window/postmessage) to send an asynchronous message to the other origin. This controlled access via message-passing is much more secure than the blanket exposure of all data caused by `document.domain`.

#### Failures

The setter will throw a "`SecurityError`" [`DOMException`](../domexception) in several cases:

- The [`document-domain`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/document-domain) [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) is disabled.
- The document is inside a sandboxed [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe).
- The document has no [browsing context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context).
- The document's [effective domain](https://html.spec.whatwg.org/multipage/origin.html#concept-origin-effective-domain) is `null`.
- The given value is neither the same as the page's current hostname, nor a parent domain of it.

As an example of this last failure case, trying to set `document.domain` to `"example.org"` when on `https://example.com/` will throw.

Additionally, as part of its deprecation, it will do nothing when combined with certain modern isolation features:

- If used on a cross-origin isolated page, i.e. one that uses the appropriate values for the [`Cross-Origin-Opener-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Opener-Policy) and [`Cross-Origin-Embedder-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Embedder-Policy) HTTP headers
- If used on an origin-isolated page, i.e. one that uses the [`Origin-Isolation`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin-Isolation) HTTP header

Finally, setting `document.domain` does not change the origin used for origin-checks by some Web APIs, preventing sub-domain access via this mechanism. Affected APIs include (but are not limited to): [`Window.localStorage`](../window/localstorage), [`IndexedDB_API`](../indexeddb_api), [`BroadcastChannel`](../broadcastchannel), [`SharedWorker`](../sharedworker) .

## Examples

### Getting the domain

For code running at the URL `https://developer.mozilla.org/en-US/docs/Web`, this example would set `currentDomain` to the string "`developer.mozilla.org`".

    const currentDomain = document.domain;

Although the getter is not dangerous in the same way that the setter is, it is likely simpler and more useful to use the [`Location.hostname`](../location/hostname) property instead. Then you can avoid `document.domain` entirely:

    const currentHostname = location.hostname;

For the URL `https://developer.mozilla.org/en-US/docs/Web`, `currentHostname` is also the string "`developer.mozilla.org`". Other alternatives that provide slightly different information are [`Location.host`](../location/host), which includes the port, and [`WindowOrWorkerGlobalScope.origin`](../windoworworkerglobalscope/origin), which provides the full origin.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/origin.html#relaxing-the-same-origin-restriction">HTML Living Standard<br />
<span class="small">The definition of 'document.domain' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

`domain`

1

12

1

From Firefox 62, if the domain cannot be identified, `domain` returns an empty string instead of `null`. See [bug 819475](https://bugzil.la/819475).

4

≤12.1

1

1

18

4

From Firefox 62, if the domain cannot be identified, `domain` returns an empty string instead of `null`. See [bug 819475](https://bugzil.la/819475).

≤12.1

1

1.0

## See also

- [Same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy)
- [`Location.hostname`](../location/hostname)
- [`Location.host`](../location/host)
- [`WindowOrWorkerGlobalScope.origin`](../windoworworkerglobalscope/origin)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/domain" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/domain</a>
