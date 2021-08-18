SVGElement
==========

All of the SVG DOM interfaces that correspond directly to elements in the SVG language derive from the `SVGElement` interface.

Properties
----------

*Also inherits properties from: <span class="page-not-created">`DocumentAndElementEventHandlers`</span>, [`Element`](element), [`ElementCSSInlineStyle`](elementcssinlinestyle), [`GlobalEventHandlers`](globaleventhandlers), [`HTMLOrForeignElement`](htmlorforeignelement), <span class="page-not-created">`SVGElementInstance`</span>*

 [`SVGElement.dataset`](htmlorforeignelement/dataset)<span class="badge inline readonly">Read only </span>   
A [`DOMStringMap`](domstringmap) object which provides a list of key/value pairs of named data attributes which correspond to [custom data attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes) attached to the element. These can also be defined in SVG using attributes of the form `data-*`, where `*` is the key name for the pair. This works just like HTML's [`HTMLElement.dataset`](htmlorforeignelement/dataset) property and HTML's [`data-*`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-data-*) global attribute.

 <span class="page-not-created">`SVGElement.className`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedString`](svganimatedstring) that reflects the value of the `class` attribute on the given element, or the empty string if `class` is not present. This attribute is deprecated and may be removed in a future version of this specification. Authors are advised to use [`Element.classList`](element/classlist) instead.

 <span class="page-not-created">`SVGElement.ownerSVGElement`</span><span class="badge inline readonly">Read only </span>   
An [`SVGSVGElement`](svgsvgelement) referring to the nearest ancestor [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element. `null` if the given element is the outermost `<svg>` element.

 <span class="page-not-created">`SVGElement.viewportElement`</span><span class="badge inline readonly">Read only </span>   
The [`SVGElement`](svgelement), which established the current viewport. Often, the nearest ancestor [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element. `null` if the given element is the outermost `<svg>` element.

Methods
-------

*This interface has no methods, but inherits methods from: <span class="page-not-created">`DocumentAndElementEventHandlers`</span>, [`Element`](element), [`ElementCSSInlineStyle`](elementcssinlinestyle), [`GlobalEventHandlers`](globaleventhandlers), [`HTMLOrForeignElement`](htmlorforeignelement), <span class="page-not-created">`SVGElementInstance`</span>*

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the equivalent `on...` handler property defined on [`GlobalEventHandlers`](globaleventhandlers) or [`WindowEventHandlers`](windoweventhandlers).

`abort`  
Fired when page loading is stopped before an SVG element has been allowed to load completely.  
Also available via the `onabort` property.

`error`  
Fired when an SVG element does not load properly or when an error occurs during script execution.  
Also available via the `onerror` property.

`load`  
Fires on an `SVGElement` when it is loaded in the browser.  
Also available via the `onload` property.

`resize`  
Fired when an SVG document is being resized.  
Also available via the `onresize` property.

`scroll`  
Fired when an SVG document view is being shifted along the X and/or Y axes.  
Also available via the `onscroll` property.

`unload`  
Fired when the DOM implementation removes an SVG document from a window or frame.  
Also available via the `onunload` property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/types.html#InterfaceSVGElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the <a href="htmlorforeignelement/dataset"><code>dataset</code></a> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGElement`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`abort_event`

?

?

?

?

?

?

?

?

?

?

?

?

`className`

22

13

20

No

15

6.1

≤37

25

20

14

7

1.5

`dataset`

55

17

51

No

41

5.1

55

55

51

41

5

6.0

`error_event`

?

?

?

?

?

?

?

?

?

?

?

?

`focus`

1

≤79

51

No

15

1.3

1

18

51

14

1

1.0

`load_event`

Yes

≤79

Yes

?

Yes

?

Yes

Yes

Yes

Yes

?

Yes

`offsetHeight`

1-50

No

No

No

≤12.1-37

3-11

1-50

18-50

No

≤12.1-37

1-11

1.0-5.0

`offsetLeft`

1-50

No

No

No

≤12.1-37

3-11

1-50

18-50

No

≤12.1-37

1-11

1.0-5.0

`offsetParent`

1-50

No

No

No

≤12.1-37

1-11

1-50

18-50

No

≤12.1-37

1-11

1.0-5.0

`offsetTop`

1-50

No

No

No

≤12.1-37

3-11

1-50

18-50

No

≤12.1-37

1-11

1.0-5.0

`offsetWidth`

1-50

No

No

No

≤12.1-37

3-11

1-50

18-50

No

≤12.1-37

1-11

1.0-5.0

`resize_event`

Yes

≤79

Yes

?

Yes

?

Yes

Yes

Yes

Yes

?

Yes

`scroll_event`

?

?

?

?

?

?

?

?

?

?

?

?

`unload_event`

?

?

?

?

?

?

?

?

?

?

?

?

See also
--------

-   HTML [`data-*`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-data-*) attribute
-   SVG `data-*` attribute
-   [Using custom data attributes in HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGElement</a>
