# Element.attachShadow()

The `Element.attachShadow()` method attaches a shadow DOM tree to the specified element and returns a reference to its [`ShadowRoot`](../shadowroot).

## Elements you can attach a shadow to

Note that you can't attach a shadow root to every type of element. There are some that can't have a shadow DOM for security reasons (for example [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)), and more besides. The following is a list of elements you **can** attach a shadow root to:

- Any autonomous custom element with a [valid name](https://html.spec.whatwg.org/multipage/custom-elements.html#valid-custom-element-name)
- [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)
- [`<aside>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside)
- [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote)
- [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)
- [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
- [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer)
- [`<h1>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)
- [`<h2>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)
- [`<h3>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)
- [`<h4>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)
- [`<h5>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)
- [`<h6>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)
- [`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header)
- [`<main>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main)
- [`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav)
- [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
- [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)
- [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)

## Syntax

    var shadowroot = element.attachShadow(shadowRootInit);

### Parameters

`shadowRootInit`  
A `ShadowRootInit` dictionary, which can contain the following fields:

`mode`  
A string specifying the _encapsulation mode_ for the shadow DOM tree. This can be one of:

- `open`: Elements of the shadow root are accessible from JavaScript outside the root, for example using [`Element.shadowRoot`](shadowroot):

      element.shadowRoot; // Returns a ShadowRoot obj

- `closed`: Denies access to the node(s) of a closed shadow root from JavaScript outside it:

      element.shadowRoot; // Returns null

`delegatesFocus`  
A boolean that, when set to `true`, specifies behavior that mitigates custom element issues around focusability. When a non-focusable part of the shadow DOM is clicked, the first focusable part is given focus, and the shadow host is given any available `:focus` styling.

### Return value

Returns a [`ShadowRoot`](../shadowroot) object.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td>The element you are trying to attach to is already a shadow host.</td></tr><tr class="even"><td><code>NotSupportedError</code></td><td>You are trying to attach a shadow root to an element outside the HTML namespace, or the element cannot have a shadow attached to it (see above).</td></tr></tbody></table>

## Examples

The following example is taken from our [word-count-web-component](https://github.com/mdn/web-components-examples/tree/master/word-count-web-component) demo ([see it live also](https://mdn.github.io/web-components-examples/word-count-web-component/)). You can see that we use `attachShadow()` in the middle of the code to create a shadow root, which we then attach our custom element's contents to.

    // Create a class for the element
    class WordCount extends HTMLParagraphElement {
      constructor() {
        // Always call super first in constructor
        super();

        // count words in element's parent element
        var wcParent = this.parentNode;

        function countWords(node){
          var text = node.innerText || node.textContent
          return text.trim().split(/\s+/g).length;
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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-attachshadow">DOM<br />
<span class="small">The definition of 'attachShadow()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`attachShadow`

53

79

63

No

40

10

53

53

63

41

10

6.0

`delegatesFocus`

Yes

79

No

No

?

?

Yes

Yes

No

?

?

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/attachShadow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/attachShadow</a>
