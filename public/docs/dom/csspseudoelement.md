# CSSPseudoElement

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSPseudoElement` interface represents a pseudo-element that may be the target of an event or animated using the [Web Animations API](web_animations_api). Instances of this interface may be obtained by calling <span class="page-not-created">`Element.pseudo()`</span>.

## Properties

[`CSSPseudoElement.element`](csspseudoelement/element) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>  
Returns the originating/parent [`Element`](element) of the pseudo-element.

[`CSSPseudoElement.type`](csspseudoelement/type) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>  
Returns the pseudo-element selector as a [`CSSOMString`](cssomstring).

## Methods

_`CSSPseudoElement` extends [`EventTarget`](eventtarget), so it inherits the following methods:_

[`EventTarget.addEventListener()`](eventtarget/addeventlistener)  
Registers an event handler of a specific event type on the pseudo-element.

[`EventTarget.dispatchEvent()`](eventtarget/dispatchevent)  
Dispatches an event to this pseudo-element.

[`EventTarget.removeEventListener()`](eventtarget/removeeventlistener)  
Removes an event listener from the pseudo-element.

## Examples

### Basic example using Element.pseudo

Using pseudo-elements, most modern browsers will automatically add quotation marks around text inside a [`<q>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q) element. (A style rule may be needed to add quotation marks in older browsers.) The example below demonstrates the basic properties of the `CSSPseudoElement` object representing the opening quotation mark.

    const element = document.querySelector('q');
    const cssPseudoElement = element.pseudo('::before');
    console.log(cssPseudoElement.element); // Outputs [object HTMLQuoteElement]
    console.log(cssPseudoElement.type); // Outputs '::before'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-pseudo-4/#CSSPseudoElement-interface">CSS Pseudo-Elements Level 4<br />
<span class="small">The definition of 'CSSPseudoElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSPseudoElement`

No

No

75

63-75

No

No

No

No

No

63-79

No

No

No

`element`

No

No

75

67-75

63-67

No

No

No

No

No

67-79

63-67

No

No

No

`type`

No

No

75

63-75

No

No

No

No

No

63-79

No

No

No

## See also

- <span class="page-not-created">`Element.pseudo()`</span>
- [Web Animations API](web_animations_api)
- [`Element.animate()`](element/animate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPseudoElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPseudoElement</a>
