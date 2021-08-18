# CustomElementRegistry.define()

The `define()` method of the [`CustomElementRegistry`](../customelementregistry) interface defines a new custom element.

There are two types of custom elements you can create:

- **Autonomous custom element**: Standalone elements; they don't inherit from built-in HTML elements.
- **Customized built-in element**: These elements inherit from — and extend — built-in HTML elements.

## Syntax

    customElements.define(name, constructor, options);

### Parameters

name  
Name for the new custom element. Note that custom element names must contain a hyphen.

constructor  
Constructor for the new custom element.

options <span class="badge inline optional">Optional</span>  
Object that controls how the element is defined. One option is currently supported:

- `extends`: String specifying the name of a built-in element to extend. Used to create a _customized built-in element_.

### Return value

Void.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>NotSupportedError</code></td><td>The <a href="../customelementregistry"><code>CustomElementRegistry</code></a> already contains an entry with the same name or the same constructor (or is otherwise already defined), or <code>extends</code> is specified and it is a <a href="https://html.spec.whatwg.org/multipage/custom-elements.html#valid-custom-element-name">valid custom element name</a>, or <code>extends</code> is specified but the element it is trying to extend is an unknown element.</td></tr><tr class="even"><td><code>SyntaxError</code></td><td>The provided name is not a <a href="https://html.spec.whatwg.org/multipage/custom-elements.html#valid-custom-element-name">valid custom element name</a>.</td></tr><tr class="odd"><td><code>TypeError</code></td><td>The referenced constructor is not a constructor.</td></tr></tbody></table>

**Note**: You'll often get `NotSupportedError`s thrown that seem like `define()` is failing, but instead it is likely a problem with [`Element.attachShadow()`](../element/attachshadow).

## Examples

### Autonomous custom element

The following code is taken from our [popup-info-box-web-component](https://github.com/mdn/web-components-examples/tree/master/popup-info-box-web-component) example ([see it live also](https://mdn.github.io/web-components-examples/popup-info-box-web-component/)).

    // Create a class for the element
    class PopUpInfo extends HTMLElement {
      constructor() {
        // Always call super first in constructor
        super();

        // Create a shadow root
        var shadow = this.attachShadow({mode: 'open'});

        // Create spans
        var wrapper = document.createElement('span');
        wrapper.setAttribute('class','wrapper');
        var icon = document.createElement('span');
        icon.setAttribute('class','icon');
        icon.setAttribute('tabindex', 0);
        var info = document.createElement('span');
        info.setAttribute('class','info');

        // Take attribute content and put it inside the info span
        var text = this.getAttribute('text');
        info.textContent = text;

        // Insert icon
        var imgUrl;
        if(this.hasAttribute('img')) {
          imgUrl = this.getAttribute('img');
        } else {
          imgUrl = 'img/default.png';
        }
        var img = document.createElement('img');
        img.src = imgUrl;
        icon.appendChild(img);

        // Create some CSS to apply to the shadow dom
        var style = document.createElement('style');

        style.textContent = '.wrapper {' +
                               'position: relative;' +
                            '}' +

                             '.info {' +
                                'font-size: 0.8rem;' +
                                'width: 200px;' +
                                'display: inline-block;' +
                                'border: 1px solid black;' +
                                'padding: 10px;' +
                                'background: white;' +
                                'border-radius: 10px;' +
                                'opacity: 0;' +
                                'transition: 0.6s all;' +
                                'position: absolute;' +
                                'bottom: 20px;' +
                                'left: 10px;' +
                                'z-index: 3;' +
                              '}' +

                              'img {' +
                                'width: 1.2rem' +
                              '}' +

                              '.icon:hover + .info, .icon:focus + .info {' +
                                'opacity: 1;' +
                              '}';

        // attach the created elements to the shadow dom

        shadow.appendChild(style);
        shadow.appendChild(wrapper);
        wrapper.appendChild(icon);
        wrapper.appendChild(info);
      }
    }

    // Define the new element
    customElements.define('popup-info', PopUpInfo);

    <popup-info img="img/alt.png" text="Your card validation code (CVC) is an extra
                                        security feature — it is the last 3 or 4
                                        numbers on the back of your card.">

**Note**: Constructors for autonomous custom elements must extend [`HTMLElement`](../htmlelement).

### Customized built-in element

The following code is taken from our [word-count-web-component](https://github.com/mdn/web-components-examples/tree/master/word-count-web-component) example ([see it live also](https://mdn.github.io/web-components-examples/word-count-web-component/)).

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

    <p is="word-count"></p>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/custom-elements.html#dom-customelementregistry-define">HTML Living Standard<br />
<span class="small">The definition of 'customElements.define()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry/define" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry/define</a>
