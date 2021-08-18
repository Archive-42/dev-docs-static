Element.insertAdjacentText()
============================

The `insertAdjacentText()` method of the [`Element`](../element) interface inserts a given text node at a given position relative to the element it is invoked upon.

Syntax
------

    element.insertAdjacentText(position, element);

### Parameters

`position`  
A [`DOMString`](../domstring) representing the position relative to the `element`; must be one of the following strings:

-   `'beforebegin'`: Before the `element` itself.
-   `'afterbegin'`: Just inside the `element`, before its first child.
-   `'beforeend'`: Just inside the `element`, after its last child.
-   `'afterend'`: After the `element` itself.

`element`  
A [`DOMString`](../domstring) representing the text to be inserted into the tree.

### Return value

Void.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>SyntaxError</code></td><td>The <code>position</code> specified is not a recognized value.</td></tr></tbody></table>

### Visualization of position names

    <!-- beforebegin -->
    <p>
      <!-- afterbegin -->
      foo
      <!-- beforeend -->
    </p>
    <!-- afterend -->

**Note:** The `beforebegin` and `afterend` positions work only if the node is in a tree and has an element parent.

Example
-------

    beforeBtn.addEventListener('click', function() {
      para.insertAdjacentText('afterbegin',textInput.value);
    });

    afterBtn.addEventListener('click', function() {
      para.insertAdjacentText('beforeend',textInput.value);
    });

Have a look at our [insertAdjacentText.html](https://mdn.github.io/dom-examples/insert-adjacent/insertAdjacentText.html) demo on GitHub (see the [source code](https://github.com/mdn/dom-examples/blob/master/insert-adjacent/insertAdjacentText.html) too.) Here we have a simple paragraph. You can enter some text into the form element, then press the *Insert before* and *Insert after* buttons to insert it before or after the existing paragraph text using `insertAdjacentText()`. Note that the existing text node is not added to — further text nodes are created containing the new additions.

Polyfill
--------

You can polyfill the insertAdjacentText`() method` in Internet Explorer 5.5 (maybe earlier) and higher with the following code:

    if (!Element.prototype.insertAdjacentText)
      Element.prototype.insertAdjacentText = function(type, txt){
        this.insertAdjacentHTML(
          type,
          (txt+'') // convert to string
            .replace(/&/g, '&amp;') // embed ampersand symbols
            .replace(/</g, '&lt;') // embed less-than symbols
        )
      }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-insertadjacenttext">DOM<br />
<span class="small">The definition of 'insertAdjacentText()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`insertAdjacentText`

1

17

12-17

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

48

5

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

≤12.1

4

2.3

18

48

≤12.1

4

1.0

See also
--------

-   [`Element.insertAdjacentElement()`](insertadjacentelement)
-   [`Element.insertAdjacentHTML()`](insertadjacenthtml)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentText</a>
