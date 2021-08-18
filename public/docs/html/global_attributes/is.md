is
==

The `is` [global attribute](../global_attributes) allows you to specify that a standard HTML element should behave like a defined custom built-in element (see [Using custom elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements) for more details).

This attribute can only be used if the specified custom element name has been successfully [defined](https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry/define) in the current document, and extends the element type it is being applied to.

Examples
--------

The following code is taken from our [word-count-web-component](https://github.com/mdn/web-components-examples/tree/master/word-count-web-component) example ([see it live also](https://mdn.github.io/web-components-examples/word-count-web-component/)).

    // Create a class for the element
    class WordCount extends HTMLParagraphElement {
      constructor() {
        // Always call super first in constructor
        super();

        // Constructor contents omitted for brevity
        ...

      }
    }

    // Define the new element
    customElements.define('word-count', WordCount, { extends: 'p' });

    <p is="word-count"></p>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/custom-elements.html#attr-is">HTML Living Standard<br />
<span class="small">The definition of 'is' in that specification.</span></a></td></tr></tbody></table>

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

`is`

67

79

63

No

54

No

See [bug 182671](https://webkit.org/b/182671).

67

67

63

48

No

See [bug 182671](https://webkit.org/b/182671).

9.0

See also
--------

-   All [global attributes](../global_attributes).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/is" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/is</a>
