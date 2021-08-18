Element.insertAdjacentElement()
===============================

The `insertAdjacentElement()` method of the [`Element`](../element) interface inserts a given element node at a given position relative to the element it is invoked upon.

Syntax
------

    targetElement.insertAdjacentElement(position, element);

### Parameters

`position`  
A [`DOMString`](../domstring) representing the position relative to the `targetElement`; must match (case-insensitively) one of the following strings:

-   `'beforebegin'`: Before the `targetElement` itself.
-   `'afterbegin'`: Just inside the `targetElement`, before its first child.
-   `'beforeend'`: Just inside the `targetElement`, after its last child.
-   `'afterend'`: After the `targetElement` itself.

`element`  
The element to be inserted into the tree.

### Return value

The element that was inserted, or `null`, if the insertion failed.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>SyntaxError</code></td><td>The <code>position</code> specified is not a recognized value.</td></tr><tr class="even"><td><code>TypeError</code></td><td>The <code>element</code> specified is not a valid element.</td></tr></tbody></table>

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
      var tempDiv = document.createElement('div');
      tempDiv.style.backgroundColor = randomColor();
      if (activeElem) {
        activeElem.insertAdjacentElement('beforebegin', tempDiv);
      }
      setListener(tempDiv);
    });

    afterBtn.addEventListener('click', function() {
      var tempDiv = document.createElement('div');
      tempDiv.style.backgroundColor = randomColor();
      if (activeElem) {
        activeElem.insertAdjacentElement('afterend', tempDiv);
      }
      setListener(tempDiv);
    });

Have a look at our [insertAdjacentElement.html](https://mdn.github.io/dom-examples/insert-adjacent/insertAdjacentElement.html) demo on GitHub (see the [source code](https://github.com/mdn/dom-examples/blob/master/insert-adjacent/insertAdjacentElement.html) too.) Here, we have a sequence of [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) elements inside a container. When one is clicked, it becomes selected and you can then press the *Insert before* and *Insert after* buttons to insert new divs before or after the selected element using `insertAdjacentElement()`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-insertadjacentelement">DOM<br />
<span class="small">The definition of 'insertAdjacentElement()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`insertAdjacentElement`

1

17

12-17

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

48

5

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

8

3

1

18

48

10.1

1

1.0

See also
--------

-   [`Element.insertAdjacentHTML()`](insertadjacenthtml)
-   [`Element.insertAdjacentText()`](insertadjacenttext)
-   [`Node.insertBefore()`](../node/insertbefore) (similar to `beforebegin`, with different arguments)
-   [`Node.appendChild()`](../node/appendchild) (same effect as `beforeend`)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentElement</a>
