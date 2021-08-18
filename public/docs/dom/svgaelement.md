SVGAElement
===========

The `SVGAElement` interface provides access to the properties of [`<a>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/a) element, as well as methods to manipulate them.

Properties
----------

*This interface also inherits properties from its parent, [`SVGGraphicsElement`](svggraphicselement), and implements properties from [`SVGURIReference`](svgurireference) and <span class="page-not-created">`HTMLHyperlinkElementUtils`</span>.*

<span class="page-not-created">`SVGAElement.download`</span>  
See [`HTMLAnchorElement.download`](htmlanchorelement/download).

<span class="page-not-created">`SVGAElement.href`</span>  
See [`HTMLAnchorElement.href`](htmlanchorelement/href).

<span class="page-not-created">`SVGAElement.hreflang`</span>  
Is a [`DOMString`](domstring) that reflects the `hreflang` attribute, indicating the language of the linked resource.

<span class="page-not-created">`SVGAElement.ping`</span>  
Is a [`DOMString`](domstring) that reflects the ping attribute, containing a space-separated list of URLs to which, when the hyperlink is followed, [`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) requests with the body `PING` will be sent by the browser (in the background). Typically used for tracking.

<span class="page-not-created">`SVGAElement.referrerPolicy`</span>  
See [`HTMLAnchorElement.referrerPolicy`](htmlanchorelement/referrerpolicy).

<span class="page-not-created">`SVGAElement.rel`</span>  
See [`HTMLAnchorElement.rel`](htmlanchorelement/rel).

<span class="page-not-created">`SVGAElement.relList`</span>  
See [`HTMLAnchorElement.relList`](htmlanchorelement/rellist).

 [`SVGAElement.target`](svgaelement/target) <span class="badge inline readonly">Read only </span>   
It corresponds to the `target` attribute of the given element.

<span class="page-not-created">`SVGAElement.text`</span>  
Is a [`DOMString`](domstring) being a synonym for the [`Node.textContent`](node/textcontent) property.

<span class="page-not-created">`SVGAElement.type`</span>  
Is a [`DOMString`](domstring) that reflects the `type` attribute, indicating the MIME type of the linked resource.

Methods
-------

*This interface has no methods but inherits methods from its parent, [`SVGGraphicsElement`](svggraphicselement).*

Example
-------

In the example below, the `target` attribute of the [`<a>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/a) element is set to `_blank` and when the link is clicked, it logs to notify whether the condition is met or not.

    var linkRef = document.querySelector("a");
    linkRef.target = "_self";

    linkRef.onclick = function(){
      if (linkRef.target === "_blank") {
        console.log("BLANK!");
        linkRef.target = "_self";
      } else {
        console.log("SORRY! not _blank");
      }
    } 

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/linking.html#InterfaceSVGAElement">Scalable Vector Graphics (SVG) 2</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Replaced inheritance from <a href="svgelement"><code>SVGElement</code></a> by <a href="svggraphicselement"><code>SVGGraphicsElement</code></a> and removed the interface implementations of <a href="svgtests"><code>SVGTests</code></a>, <span class="page-not-created"><code>SVGLangSpace</code></span>, <a href="svgexternalresourcesrequired"><code>SVGExternalResourcesRequired</code></a>, <a href="svgstylable"><code>SVGStylable</code></a>, and <a href="svgtransformable"><code>SVGTransformable</code></a> by <span class="page-not-created"><code>HTMLHyperlinkElementUtils</code></span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/linking.html#InterfaceSVGAElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGAElement`

1

12

3

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`download`

No

No

20

No

No

No

No

No

20

No

No

No

`hreflang`

No

≤18-79

61

No

No

No

No

No

61

No

No

No

`ping`

No

No

61

No

No

No

No

No

61

No

No

No

`referrerPolicy`

No

No

52

No

No

No

No

No

52

No

No

No

`rel`

No

≤18-79

61

No

No

14

No

No

61

No

14

No

`relList`

No

≤18-79

61

No

No

14

No

No

61

No

14

No

`target`

1

12

3

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`text`

No

≤18-79

61

No

No

No

No

No

61

No

No

No

`type`

No

≤18-79

61

No

No

No

No

No

61

No

No

No

See also
--------

-   SVG [`<a>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/a) element

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAElement</a>
