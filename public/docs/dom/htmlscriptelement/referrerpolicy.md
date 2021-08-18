HTMLScriptElement.referrerPolicy
================================

The `referrerPolicy` property of the [`HTMLScriptElement`](../htmlscriptelement) interface reflects the HTML [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attr-referrerpolicy) of the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element and fetches made by that script, defining which referrer is sent when fetching the resource.

Syntax
------

    refStr = scriptElem.referrerPolicy;
    scriptElem.referrerPolicy = refStr;

### Value

A [`DOMString`](../domstring); one of the following:

no-referrer  
The [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header will be omitted entirely. No referrer information is sent along with requests.

no-referrer-when-downgrade (default)  
This is the user agent's default behavior if no policy is specified. The URL is sent as a referrer when the protocol security level stays the same (e.g.HTTP→HTTP, HTTPS→HTTPS), but isn't sent to a less secure destination (e.g. HTTPS→HTTP).

origin  
Only send the origin of the document as the referrer in all cases.  
The document `https://example.com/page.html` will send the referrer `https://example.com/`.

origin-when-cross-origin  
Send a full URL when performing a same-origin request, but only send the origin of the document for other cases.

same-origin  
A referrer will be sent for [same-site origins](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy), but cross-origin requests will contain no referrer information.

strict-origin  
Only send the origin of the document as the referrer when the protocol security level stays the same (e.g. HTTPS→HTTPS), but don't send it to a less secure destination (e.g. HTTPS→HTTP).

strict-origin-when-cross-origin  
Send a full URL when performing a same-origin request, only send the origin when the protocol security level stays the same (e.g. HTTPS→HTTPS), and send no header to a less secure destination (e.g. HTTPS→HTTP).

unsafe-url  
Send a full URL when performing a same-origin or cross-origin request. This policy will leak origins and paths from TLS-protected resources to insecure origins. Carefully consider the impact of this setting.

**Note**: An empty string value (`""`) is both the default value, and a fallback value if `referrerpolicy` is not supported. If `referrerpolicy` is not explicitly specified on the `<script>` element, it will adopt a higher-level referrer policy, i.e. one set on the whole document or domain. If a higher-level policy is not available, the empty string is treated as being equivalent to `no-referrer-when-downgrade`.

Examples
--------

    var scriptElem = document.createElement("script");
    scriptElem.src = "/";
    scriptElem.referrerPolicy = "unsafe-url";
    document.body.appendChild(scriptElem);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-referrer-attribute">Referrer Policy<br />
<span class="small">The definition of 'referrerpolicy attribute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>referrerPolicy</code> attribute.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/#dom-script-referrerpolicy">HTML Living Standard<br />
<span class="small">The definition of 'HTMLScriptElement: referrerPolicy' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`referrerPolicy`

70

79

65

No

57

14

70

70

65

49

14

10.0

See also
--------

-   [`HTMLIFrameElement.referrerPolicy`](../htmliframeelement/referrerpolicy)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement/referrerPolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement/referrerPolicy</a>
