HTMLIFrameElement
=================

The `HTMLIFrameElement` interface provides special properties and methods (beyond those of the [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating the layout and presentation of inline frame elements.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement)*.

 <span class="page-not-created">`HTMLIFrameElement.align`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) that specifies the alignment of the frame with respect to the surrounding context.

 <span class="page-not-created">`HTMLIFrameElement.allow`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is a list of origins the frame is allowed to display content from. This attribute also accepts the values `self` and `src` which represent the origin in the iframe's src attribute. The default value is `src`.

 <span class="page-not-created">`HTMLIFrameElement.allowfullscreen`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the inline frame is willing to be placed into full screen mode. See [Using full-screen mode](fullscreen_api) for details.

[`HTMLIFrameElement.allowPaymentRequest`](htmliframeelement/allowpaymentrequest)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the [Payment Request API](payment_request_api) may be invoked inside a cross-origin iframe.

 [`HTMLIFrameElement.contentDocument`](htmliframeelement/contentdocument) <span class="badge inline readonly">Read only </span>   
Returns a [`Document`](document), the active document in the inline frame's nested browsing context.

 [`HTMLIFrameElement.contentWindow`](htmliframeelement/contentwindow) <span class="badge inline readonly">Read only </span>   
Returns a <span class="page-not-created">`WindowProxy`</span>, the window proxy for the nested browsing context.

[`HTMLIFrameElement.csp`](htmliframeelement/csp)  
Specifies the Content Security Policy that an embedded document must agree to enforce upon itself.

 <span class="page-not-created">`HTMLIFrameElement.frameBorder`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) that indicates whether to create borders between frames.

<span class="page-not-created">`HTMLIFrameElement.height`</span>  
Is a [`DOMString`](domstring) that reflects the [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-height) HTML attribute, indicating the height of the frame.

 <span class="page-not-created">`HTMLIFrameElement.longDesc`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) that contains the URI of a long description of the frame.

 <span class="page-not-created">`HTMLIFrameElement.marginHeight`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) being the height of the frame margin.

 <span class="page-not-created">`HTMLIFrameElement.marginWidth`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) being the width of the frame margin.

<span class="page-not-created">`HTMLIFrameElement.name`</span>  
Is a [`DOMString`](domstring) that reflects the [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-name) HTML attribute, containing a name by which to refer to the frame.

 [`HTMLIFrameElement.featurePolicy`](htmliframeelement/featurepolicy) <span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns the [`FeaturePolicy`](featurepolicy) interface which provides a simple API for introspecting the feature policies applied to a specific document.

 [`HTMLIFrameElement.referrerPolicy`](htmliframeelement/referrerpolicy) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is a [`DOMString`](domstring) that reflects the [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-referrerpolicy) HTML attribute indicating which referrer to use when fetching the linked resource.

<span class="page-not-created">`HTMLIFrameElement.sandbox`</span>  
Is a <span class="page-not-created">`DOMSettableTokenList`</span> that reflects the [`sandbox`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-sandbox) HTML attribute, indicating extra restrictions on the behavior of the nested content.

 <span class="page-not-created">`HTMLIFrameElement.scrolling`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) that indicates whether the browser should provide scrollbars for the frame.

[`HTMLIFrameElement.src`](htmliframeelement/src)  
Is a [`DOMString`](domstring) that reflects the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-src) HTML attribute, containing the address of the content to be embedded. Note that programmatically removing an `<iframe>`'s src attribute (e.g. via [`Element.removeAttribute()`](element/removeattribute)) causes `about:blank` to be loaded in the frame in Firefox (from version 65), Chromium-based browsers, and Safari/iOS.

[`HTMLIFrameElement.srcdoc`](htmliframeelement/srcdoc)  
Is a [`DOMString`](domstring) that represents the content to display in the frame.

<span class="page-not-created">`HTMLIFrameElement.width`</span>  
Is a [`DOMString`](domstring) that reflects the [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-width) HTML attribute, indicating the width of the frame.

Methods
-------

*Inherits properties from its parent, [`HTMLElement`](htmlelement)*.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmliframeelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLIFrameElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>The following property has been added: <code>allowFullscreen</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#the-iframe-element">HTML5<br />
<span class="small">The definition of 'HTMLIFrameElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The following properties are now obsolete: <code>scrolling</code>, <code>marginWidth</code>, <code>marginHeight</code>, <code>longDesc</code>, <code>frameBorder</code>, and <code>align</code>.<br />
The following properties have been added: <code>srcdoc</code>, <code>sandbox</code>, and <code>contentWindow</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-50708718">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLIFrameElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>contentDocument</code> property has been added.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-50708718">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLIFrameElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLIFrameElement`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`align`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`allow`

60

79

74

No

53

11.1

66

66

79

47

11.3

9.0

`allowFullscreen`

38

12

22

9-18

No

25

10.1

38

38

22

9-18

25

10.3

3.0

`allowPaymentRequest`

60

15

56-83

No

No

No

No

61

56-83

No

No

No

`contentDocument`

1

12

1

8

≤12.1

3

1

18

4

≤12.1

1

1.0

`contentWindow`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`csp`

61

79

No

No

48

No

61

61

No

45

No

8.0

`featurePolicy`

74

73-74

69-73

79

69

65-69

No

62

60-62

56-60

No

74

74

73-74

69-73

65

48

No

11.0

`frameBorder`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`getSVGDocument`

1

12

3.5

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

`height`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`loading`

77

79

No

No

60

No

See [bug 196698](https://webkit.org/b/196698)

77

77

No

55

No

See [bug 196698](https://webkit.org/b/196698)

12.0

`longDesc`

1

12

1

6

≤12.1

3

1

18

4

≤12.1

1

1.0

`marginHeight`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`marginWidth`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`name`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

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

`sandbox`

5

Before Chrome 50, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

12

17

Previously, the type of `sandbox` was a `DOMString` instead of a `DOMSettableTokenList`. This has been fixed with Firefox 29. Other browsers may still implement the property as `DOMString` since it was a late change in the specification.

10

15

Before Opera 37, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

5

1

Before WebView 50, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

18

Before Chrome 50, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

17

Previously, the type of `sandbox` was a `DOMString` instead of a `DOMSettableTokenList`. This has been fixed with Firefox 29. Other browsers may still implement the property as `DOMString` since it was a late change in the specification.

14

Before Opera 37, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

4

1.0

Before Samsung Internet 5.0, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

`scrolling`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`src`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`srcdoc`

20

79

25

No

15

6

≤37

25

25

14

6

1.5

`width`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   The HTML element implementing this interface: [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement</a>
