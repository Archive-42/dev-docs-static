# HTMLImageElement.referrerPolicy

The ` HTMLImageElement``.referrerPolicy ` property reflects the HTML [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-referrerpolicy) attribute of the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element defining which referrer is sent when fetching the resource.

## Syntax

    refStr = imgElt.referrerPolicy;
    imgElt.referrerPolicy = refStr;

### Values

A [`DOMString`](../domstring) representing the referrer policy. Possible values are:

- `"no-referrer"` meaning that the `Referer:` HTTP header will not be sent.
- `"origin"` meaning that the referrer will be the origin of the page, that is roughly the scheme, the host and the port.
- `"unsafe-url"` meaning that the referrer will include the origin and the path (but not the fragment, password, or username). This case is unsafe as it can leak path information that has been concealed to third-party by using TLS.

## Examples

    var img = new Image();
    img.src = 'img/logo.png';
    img.referrerPolicy = 'origin';

    var div = document.getElementById('divAround');
    div.appendChild(img); // Fetch the image using the origin as the referrer

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-referrer-attribute">Referrer Policy<br />
<span class="small">The definition of 'referrerPolicy attribute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>referrerPolicy</code> property.</td></tr></tbody></table>

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

40

14

53

53

50

41

14

6.0

## See also

- [`HTMLAnchorElement.referrerPolicy`](../htmlanchorelement/referrerpolicy), [`HTMLAreaElement.referrerPolicy`](../htmlareaelement/referrerpolicy), and [`HTMLIFrameElement.referrerPolicy`](../htmliframeelement/referrerpolicy).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/referrerPolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/referrerPolicy</a>
