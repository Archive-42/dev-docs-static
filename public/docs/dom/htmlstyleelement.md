# HTMLStyleElement

The `HTMLStyleElement` interface represents a [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) element. It inherits properties and methods from its parent, [`HTMLElement`](htmlelement), and from [`LinkStyle`](linkstyle).

This interface doesn't allow to manipulate the CSS it contains (in most case). To manipulate CSS, see [Using dynamic styling information](css_object_model/using_dynamic_styling_information) for an overview of the objects used to manipulate specified CSS properties using the DOM.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement), and implements [`LinkStyle`](linkstyle)._

[`HTMLStyleElement.media`](htmlstyleelement/media)  
Is a [`DOMString`](domstring) representing the intended destination medium for style information.

[`HTMLStyleElement.type`](htmlstyleelement/type) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) representing the type of style being applied by this statement.

<span class="page-not-created">`HTMLStyleElement.disabled`</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value representing whether or not the stylesheet is disabled (true) or not (false).

<span class="page-not-created">`LinkStyle.sheet`</span> <span class="badge inline readonly">Read only </span>  
Returns the [`StyleSheet`](stylesheet) object associated with the given element, or `null` if there is none

[`HTMLStyleElement.scoped`](htmlstyleelement/scoped) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating if the element applies to the whole document (`false`) or only to the parent's sub-tree (`true`).

## Methods

_No specific method; inherits properties from its parent, [`HTMLElement`](htmlelement), and [`LinkStyle`](linkstyle)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlstyleelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLStyleElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/document-metadata.html#the-style-element">HTML 5.1<br />
<span class="small">The definition of 'HTMLStyleElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/document-metadata.html#the-style-element">HTML5<br />
<span class="small">The definition of 'HTMLStyleElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The following property has been added: <code>scoped</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-16428977">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLStyleElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added a second inheritence, the <a href="linkstyle"><code>LinkStyle</code></a> interface.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-16428977">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLStyleElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`HTMLStyleElement`

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

`disabled`

1

13

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

`scoped`

19-35

No

55-61

This property was hidden behind a pref because no other browsers support it (See [bug 1291515](https://bugzil.la/1291515)).

21-55

No

No

No

No

No

55-61

This property was hidden behind a pref because no other browsers support it (See [bug 1291515](https://bugzil.la/1291515)).

21-55

No

No

No

`sheet`

1

12

1

9

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

- The HTML element implementing this interface: [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style).
- [Using dynamic styling information](css_object_model/using_dynamic_styling_information) to see how to manipulate CSS.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement</a>
