Element.lastElementChild
========================

The `Element.lastElementChild` read-only property returns an element's last child [`Element`](../element), or `null` if there are no child elements.

`Element.lastElementChild` includes only element nodes. To get all child nodes, including non-element nodes like text and comment nodes, use [`Node.lastChild`](../node/lastchild).

Syntax
------

    // Getter
    element = el.lastElementChild;

    // No setter; read-only property

Example
-------

    <ul id="list">
      <li>First  (1)</li>
      <li>Second (2)</li>
      <li>Third  (3)</li>
    </ul>

    <script>
    const list = document.getElementById('list');
    console.log(list.lastElementChild.textContent);
    // logs "Third (3)"
    </script>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-lastelementchild">DOM<br />
<span class="small">The definition of 'ParentNode.lastElementChild' in that specification.</span></a></td></tr></tbody></table>

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

`lastElementChild`

1

12

3.5

9

10

4

1

18

4

10.1

3

1.0

See also
--------

-   [`Element.previousElementSibling`](previouselementsibling)
-   [`Element.firstElementChild`](firstelementchild)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/lastElementChild" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/lastElementChild</a>
