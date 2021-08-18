# HTMLObjectElement

The `HTMLObjectElement` interface provides special properties and methods (beyond those on the [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating the layout and presentation of [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object) element, representing external resources.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

<span class="page-not-created">`HTMLObjectElement.align`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) representing an enumerated property indicating alignment of the element's contents with respect to the surrounding context. The possible values are `"left"`, `"right"`, `"justify"`, and `"center"`.

<span class="page-not-created">`HTMLObjectElement.archive`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) that reflects the [`archive`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-archive) HTML attribute, containing a list of archives for resources for this object.

<span class="page-not-created">`HTMLObjectElement.border`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) that reflects the [`border`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-border) HTML attribute, specifying the width of a border around the object.

<span class="page-not-created">`HTMLObjectElement.code`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) representing the name of an applet class file, containing either the applet's subclass, or the path to get to the class, including the class file itself.

<span class="page-not-created">`HTMLObjectElement.codeBase`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) that reflects the [`codebase`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-codebase) HTML attribute, specifying the base path to use to resolve relative URIs.

<span class="page-not-created">`HTMLObjectElement.codeType`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) that reflects the [`codetype`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-codetype) HTML attribute, specifying the content type of the data.

[`HTMLObjectElement.contentDocument`](htmlobjectelement/contentdocument) <span class="badge inline readonly">Read only </span>  
Returns a [`Document`](document) representing the active document of the object element's nested browsing context, if any; otherwise `null`.

[`HTMLObjectElement.contentWindow`](htmlobjectelement/contentwindow) <span class="badge inline readonly">Read only </span>  
Returns a <span class="page-not-created">`WindowProxy`</span> representing the window proxy of the object element's nested browsing context, if any; otherwise `null`.

[`HTMLObjectElement.data`](htmlobjectelement/data)  
Returns a [`DOMString`](domstring) that reflects the [`data`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-data) HTML attribute, specifying the address of a resource's data.

<span class="page-not-created">`HTMLObjectElement.declare`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the [`declare`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-declare) HTML attribute, indicating that this is a declaration, not an instantiation, of the object.

[`HTMLObjectElement.form`](htmlobjectelement/form) <span class="badge inline readonly">Read only </span>  
Returns a [`HTMLFormElement`](htmlformelement) representing the object element's form owner, or null if there isn't one.

[`HTMLObjectElement.height`](htmlobjectelement/height)  
Returns a [`DOMString`](domstring) that reflects the [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-height) HTML attribute, specifying the displayed height of the resource in CSS pixels.

<span class="page-not-created">`HTMLObjectElement.hspace`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a `long` representing the horizontal space in pixels around the control.

[`HTMLObjectElement.name`](htmlobjectelement/name)  
Returns a [`DOMString`](domstring) that reflects the [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-name) HTML attribute, specifying the name of the browsing context.

<span class="page-not-created">`HTMLObjectElement.standby`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) that reflects the [`standby`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-standby) HTML attribute, specifying a message to display while the object loads.

[`HTMLObjectElement.type`](htmlobjectelement/type)  
Is a [`DOMString`](domstring) that reflects the [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-type) HTML attribute, specifying the MIME type of the resource.

[`HTMLObjectElement.useMap`](htmlobjectelement/usemap)  
Is a [`DOMString`](domstring) that reflects the [`usemap`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-usemap) HTML attribute, specifying a [`<map>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map) element to use.

[`HTMLObjectElement.validationMessage`](htmlobjectelement/validationmessage) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) representing a localized message that describes the validation constraints that the control does not satisfy (if any). This is the empty string if the control is not a candidate for constraint validation (`willValidate` is `false`), or it satisfies its constraints.

[`HTMLObjectElement.validity`](htmlobjectelement/validity) <span class="badge inline readonly">Read only </span>  
Returns a [`ValidityState`](validitystate) with the validity states that this element is in.

<span class="page-not-created">`HTMLObjectElement.vspace`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a `long` representing the horizontal space in pixels around the control.

[`HTMLObjectElement.width`](htmlobjectelement/width)  
Is a [`DOMString`](domstring) that reflects the [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object#attr-width) HTML attribute, specifying the displayed width of the resource in CSS pixels.

[`HTMLObjectElement.willValidate`](htmlobjectelement/willvalidate) <span class="badge inline readonly">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the element is a candidate for constraint validation. Always `false` for `HTMLObjectElement` objects.

## Methods

_Inherits methods from its parent, [`HTMLElement`](htmlelement)._

[`HTMLObjectElement.checkValidity()`](htmlobjectelement/checkvalidity)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that always is `true`, because `object` objects are never candidates for constraint validation.

[`HTMLObjectElement.setCustomValidity()`](htmlobjectelement/setcustomvalidity)  
Sets a custom validity message for the element. If this message is not the empty string, then the element is suffering from a custom validity error, and does not validate.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlobjectelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLObjectElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-9893177">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLObjectElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>contentDocument</code> property has been added.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-9893177">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLObjectElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLObjectElement`

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

`archive`

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

`border`

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

`checkValidity`

10

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`code`

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

`codeBase`

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

`codeType`

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

53

17

22

No

No

13

53

53

22

No

13

6.0

`data`

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

`declare`

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

`form`

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

3

1

18

4

≤12.1

1

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

`hspace`

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

`reportValidity`

39

18

49

No

26

10.1

39

39

49

26

10.3

4.0

`setCustomValidity`

10

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`standby`

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

`type`

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

`useMap`

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

`validationMessage`

10

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`validity`

10

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`vspace`

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

`willValidate`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

4

1.0

## See also

- The HTML element implementing this interface: [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement</a>
