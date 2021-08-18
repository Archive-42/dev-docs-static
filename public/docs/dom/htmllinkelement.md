# HTMLLinkElement

The `HTMLLinkElement` interface represents reference information for external resources and the relationship of those resources to a document and vice-versa (corresponds to `<link>` element; not to be confused with `<a>`, which is represented by `HTMLAnchorElement`). This object inherits all of the properties and methods of the [`HTMLElement`](htmlelement) interface.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement), and [`LinkStyle`](linkstyle)._

[`HTMLLinkElement.as`](htmllinkelement/as)  
Is a [`DOMString`](domstring) representing the type of content being loaded by the HTML link.

<span class="page-not-created">`HTMLLinkElement.crossOrigin`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is a [`DOMString`](domstring) that corresponds to the CORS setting for this link element. See [CORS settings attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin) for details.

<span class="page-not-created">`HTMLLinkElement.disabled`</span>  
Is a `Boolean` which represents whether the link is disabled; currently only used with style sheet links.

<span class="page-not-created">`HTMLLinkElement.href`</span>  
Is a [`DOMString`](domstring) representing the URI for the target resource.

<span class="page-not-created">`HTMLLinkElement.hreflang`</span>  
Is a [`DOMString`](domstring) representing the language code for the linked resource.

<span class="page-not-created">`HTMLLinkElement.media`</span>  
Is a [`DOMString`](domstring) representing a list of one or more media formats to which the resource applies.

[`HTMLLinkElement.referrerPolicy`](htmllinkelement/referrerpolicy) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is a [`DOMString`](domstring) that reflects the [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#attr-referrerpolicy) HTML attribute indicating which referrer to use.

[`HTMLLinkElement.rel`](htmllinkelement/rel)  
Is a [`DOMString`](domstring) representing the forward relationship of the linked resource from the document to the resource.

[`HTMLLinkElement.relList`](htmllinkelement/rellist) <span class="badge inline readonly">Read only </span>  
Is a [`DOMTokenList`](domtokenlist) that reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#attr-rel) HTML attribute, as a list of tokens.

<span class="page-not-created">`HTMLLinkElement.sizes`</span> <span class="badge inline readonly">Read only </span>  
Is a <span class="page-not-created">`DOMSettableTokenList`</span> that reflects the [`sizes`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#attr-sizes) HTML attribute, as a list of tokens.

<span class="page-not-created">`LinkStyle.sheet`</span> <span class="badge inline readonly">Read only </span>  
Returns the [`StyleSheet`](stylesheet) object associated with the given element, or `null` if there is none.

<span class="page-not-created">`HTMLLinkElement.type`</span>  
Is a [`DOMString`](domstring) representing the MIME type of the linked resource.

### Obsolete properties

<span class="page-not-created">`HTMLLinkElement.charset`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) representing the character encoding for the target resource.

<span class="page-not-created">`HTMLLinkElement.rev`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) representing the reverse relationship of the linked resource from the resource to the document.

**Note**: Currently the W3C HTML 5.2 spec states that `rev` is no longer obsolete, whereas the WHATWG living standard still has it labeled obsolete. Until this discrepancy is resolved, you should still assume it is obsolete.

<span class="page-not-created">`HTMLLinkElement.target`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) representing the name of the target frame to which the resource applies.

## Methods

_No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement), and [`LinkStyle`](linkstyle)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/preload/">Preload</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines <code>&lt;link rel="preload"&gt;</code>, and the <code>as</code> property. Note that currently Firefox only supports preloading of cacheable resources.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/#htmllinkelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLLinkElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Adds the following properties: <code>crossOrigin</code>, <code>referrerPolicy</code>, and <code>as</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html51/document-metadata.html#the-link-element">HTML 5.1<br />
<span class="small">The definition of 'HTMLLinkElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/document-metadata.html#the-link-element">HTML5<br />
<span class="small">The definition of 'HTMLLinkElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The following properties are now obsolete: <code>charset</code>, <code>rev</code>, and <code>shape</code>.<br />
The following properties have been added: <code>relList</code>, and <code>sizes</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-35143001">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLLinkElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added a second inheritence, the <a href="linkstyle"><code>LinkStyle</code></a> interface.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-35143001">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLLinkElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLLinkElement`

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

`as`

50

17

56

No

37

10

50

50

56

37

10

5.0

`charset`

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

`crossOrigin`

34

17

18

No

21

10

37

34

18

21

10

2.0

`disabled`

1

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

12

Since Edge 79, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

1

5.5

≤12.1

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

3

1

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

18

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

4

≤12.1

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

1

1.0

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

`href`

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

`hreflang`

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

`imageSizes`

73

79

78

No

60

No

73

73

79

52

No

11.0

`imageSrcset`

73

79

78

No

60

No

73

73

79

52

No

11.0

`integrity`

45

17

43

No

32

11.1

45

45

43

32

11.3

5.0

`media`

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

58

79

50

No

45

14.1

58

58

50

43

14.5

7.0

`rel`

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

`relList`

50

17

30

No

37

9

50

50

30

37

9

5.0

`rev`

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

`sizes`

15

Before Chrome 50, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

79

31

No

15

Before Opera 37, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

6

≤37

Before WebView 50, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

18

Before Chrome 50, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

31

14

Before Opera 37, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

6

1.0

Before Samsung Internet 5.0, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

`target`

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

## See also

- The HTML element implementing this interface: [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement</a>
