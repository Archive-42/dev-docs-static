# HTMLIFrameElement.referrerPolicy

The ` HTMLIFrameElement``.referrerPolicy ` property reflects the HTML [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-referrerpolicy) attribute of the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) element defining which referrer is sent when fetching the resource.

## Syntax

    refStr = iframeElt.referrerPolicy;
    iframeElt.referrerPolicy = refStr;

### Values

no-referrer  
The [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header will be omitted entirely. No referrer information is sent along with requests.

no-referrer-when-downgrade  
The URL is sent as a referrer when the protocol security level stays the same (HTTP→HTTP, HTTPS→HTTPS), but isn't sent to a less secure destination (HTTPS→HTTP).

origin  
Only send the origin of the document as the referrer in all cases.  
The document `https://example.com/page.html` will send the referrer `https://example.com/`.

origin-when-cross-origin  
Send a full URL when performing a same-origin request, but only send the origin of the document for other cases.

same-origin  
A referrer will be sent for [same-site origins](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy), but cross-origin requests will contain no referrer information.

strict-origin  
Only send the origin of the document as the referrer when the protocol security level stays the same (HTTPS→HTTPS), but don't send it to a less secure destination (HTTPS→HTTP).

strict-origin-when-cross-origin (default)  
This is the user agent's default behavior if no policy is specified. Send a full URL when performing a same-origin request, only send the origin when the protocol security level stays the same (HTTPS→HTTPS), and send no header to a less secure destination (HTTPS→HTTP).

unsafe-url  
Send a full URL when performing a same-origin or cross-origin request.

This policy will leak origins and paths from TLS-protected resources to insecure origins. Carefully consider the impact of this setting.

## Examples

    var iframe = document.createElement("iframe");
    iframe.src = "/";
    iframe.referrerPolicy = "unsafe-url";
    var body = document.getElementsByTagName("body")[0];
    body.appendChild(iframe); // Fetch the image using the complete URL as the referrer

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-referrer-attribute">Referrer Policy<br />
<span class="small">The definition of 'referrerpolicy attribute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>referrerPolicy</code> attribute.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/#dom-iframe-referrerpolicy">HTML Living Standard<br />
<span class="small">The definition of 'HTMLIFrameElement: referrerPolicy' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`referrerPolicy`

53

79

50

No

38

14

53

53

50

41

14

6.0

## See also

- [`HTMLAnchorElement.referrerPolicy`](../htmlanchorelement/referrerpolicy), [`HTMLAreaElement.referrerPolicy`](../htmlareaelement/referrerpolicy), and [`HTMLAreaElement.referrerPolicy`](../htmlareaelement/referrerpolicy).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/referrerPolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/referrerPolicy</a>
