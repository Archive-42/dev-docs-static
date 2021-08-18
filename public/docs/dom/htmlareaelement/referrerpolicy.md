HTMLAreaElement.referrerPolicy
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `HTMLAreaElement``.referrerPolicy` property reflect the HTML [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-referrerpolicy) attribute of the [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) element defining which referrer is sent when fetching the resource.

Syntax
------

    refStr = areaElt.referrerPolicy;
    areaElt.referrerPolicy = refStr;

### Values

-   `"no-referrer"` meaning that the `Referer:` HTTP header will not be sent.
-   `"origin"` meaning that the referrer will be the origin of the page, that is roughly the scheme, the host and the port.
-   `"unsafe-url"` meaning that the referrer will include the origin and the path (but not the fragment, password, or username). This case is unsafe as it can leak path information that has been concealed to third-party by using TLS.

Examples
--------

    <img usemap="#mapAround" width="100" height="100" src="/img/logo@2x.png" />
    <map id="myMap" name="mapAround" />>

    var elt = document.createElement("area");
    elt.href = "/img2.png";
    elt.shape = "rect";
    elt.referrerPolicy = "no-referrer";
    elt.coords = "0,0,100,100";
    var map = document.getElementById("myMap");

    map.appendChild(elt);
    // When clicked, the area's link will not send a referrer header.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-referrer-attribute">Referrer Policy<br />
<span class="small">The definition of 'referrerpolicy attribute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>referrerPolicy</code> property.</td></tr></tbody></table>

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

53

79

50

No

40

14.1

53

53

50

41

14.5

7.2

See also
--------

-   [`HTMLImageElement.referrerPolicy`](../htmlimageelement/referrerpolicy), [`HTMLAnchorElement.referrerPolicy`](../htmlanchorelement/referrerpolicy), and [`HTMLIFrameElement.referrerPolicy`](../htmliframeelement/referrerpolicy).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/referrerPolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/referrerPolicy</a>
