# Element.ariaRelevant

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ariaRelevant` property of the [`Element`](../element) interface reflects the value of the [`aria-relevant`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-relevant_attribute) attribute, which indicates what notifications the user agent will trigger when the accessibility tree within a live region is modified. This is used to describe what changes in an `aria-live` region are relevant and should be announced.

## Syntax

    var ariaRelevant = element.ariaRelevant;
    element.ariaRelevant = ariaRelevant

### Value

A [`DOMString`](../domstring) containing one or more of the following values, space separated:

"additions"  
Additions of Element Nodes within the live region should be considered relevant.

"removals"  
Deletion of Nodes from the live region should be considered relevant.

"text"  
Changes to the textual content of existing nodes should be considered relevant.

"all"  
Equivalent to `"additions removals text"`.

## Examples

In this example the `aria-relevant` attribute on the element with an ID of `text` is set to "all". Using `ariaRelevant` we update the value to "text".

    <div id="clock" role="timer" aria-live="polite" aria-atomic="true" aria-relevant="all"></div>

    let el = document.getElementById('clock');
    console.log(el.ariaRelevant); // all
    el.ariaRelevant = "text"
    console.log(el.ariaRelevant); // text

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

`ariaRelevant`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRelevant" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRelevant</a>
