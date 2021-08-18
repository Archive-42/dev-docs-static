# CustomElementRegistry

The `CustomElementRegistry` interface provides methods for registering custom elements and querying registered elements. To get an instance of it, use the [`window.customElements`](window/customelements) property.

## Methods

[`CustomElementRegistry.define()`](customelementregistry/define)  
Defines a new [custom element](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements).

[`CustomElementRegistry.get()`](customelementregistry/get)  
Returns the constructor for the named custom element, or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) if the custom element is not defined.

[`CustomElementRegistry.upgrade()`](customelementregistry/upgrade)  
Upgrades a custom element directly, even before it is connected to its shadow root.

[`CustomElementRegistry.whenDefined()`](customelementregistry/whendefined)  
Returns an empty [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when a custom element becomes defined with the given name. If such a custom element is already defined, the returned promise is immediately fulfilled.

## Examples

The following code is taken from our [word-count-web-component](https://github.com/mdn/web-components-examples/tree/master/word-count-web-component) example ([see it live also](https://mdn.github.io/web-components-examples/word-count-web-component/)). Note how we use the [`CustomElementRegistry.define()`](customelementregistry/define) method to define the custom element after creating its class.

    // Create a class for the element
    class WordCount extends HTMLParagraphElement {
      constructor() {
        // Always call super first in constructor
        super();

        // count words in element's parent element
        var wcParent = this.parentNode;

        function countWords(node){
          var text = node.innerText || node.textContent
          return text.split(/\s+/g).length;
        }

        var count = 'Words: ' + countWords(wcParent);

        // Create a shadow root
        var shadow = this.attachShadow({mode: 'open'});

        // Create text node and add word count to it
        var text = document.createElement('span');
        text.textContent = count;

        // Append it to the shadow root
        shadow.appendChild(text);

        // Update count when element content changes
        setInterval(function() {
          var count = 'Words: ' + countWords(wcParent);
          text.textContent = count;
        }, 200)

      }
    }

    // Define the new element
    customElements.define('word-count', WordCount, { extends: 'p' });

**Note:** The `CustomElementRegistry` is available through the [`Window.customElements`](window/customelements) property.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/custom-elements.html#customelementregistry">HTML Living Standard<br />
<span class="small">The definition of 'CustomElementRegistry' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CustomElementRegistry`

54

79

63

No

41

10.1

54

54

63

41

10.3

6.0

`builtin`

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

`define`

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

79

Support for 'Customized built-in elements' as well.

79

Support for 'Autonomous custom elements' only.

63

No

54

Support for 'Customized built-in elements' as well.

41

Support for 'Autonomous custom elements' only.

10.1

Supports 'Autonomous custom elements' but not 'Customized built-in elements'

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

63

48

Support for 'Customized built-in elements' as well.

41

Support for 'Autonomous custom elements' only.

10.3

Supports 'Autonomous custom elements' but not 'Customized built-in elements'

9.0

Support for 'Customized built-in elements' as well.

6.0

Support for 'Autonomous custom elements' only.

`get`

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

79

Support for 'Customized built-in elements' as well.

79

Support for 'Autonomous custom elements' only.

63

No

54

Support for 'Customized built-in elements' as well.

41

Support for 'Autonomous custom elements' only.

10.1

Supports 'Autonomous custom elements' but not 'Customized built-in elements'

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

63

48

Support for 'Customized built-in elements' as well.

41

Support for 'Autonomous custom elements' only.

10.3

Supports 'Autonomous custom elements' but not 'Customized built-in elements'

9.0

Support for 'Customized built-in elements' as well.

6.0

Support for 'Autonomous custom elements' only.

`upgrade`

68

79

63

No

55

12.1

68

68

63

48

12.2

10.0

`whenDefined`

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

79

Support for 'Customized built-in elements' as well.

79

Support for 'Autonomous custom elements' only.

63

No

54

Support for 'Customized built-in elements' as well.

41

Support for 'Autonomous custom elements' only.

10.1

Supports 'Autonomous custom elements' but not 'Customized built-in elements'

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

63

48

Support for 'Customized built-in elements' as well.

41

Support for 'Autonomous custom elements' only.

10.3

Supports 'Autonomous custom elements' but not 'Customized built-in elements'

9.0

Support for 'Customized built-in elements' as well.

6.0

Support for 'Autonomous custom elements' only.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry</a>
