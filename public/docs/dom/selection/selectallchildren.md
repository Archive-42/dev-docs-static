Selection.selectAllChildren()
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.selectAllChildren()` method adds all the children of the specified node to the selection. Previous selection is lost.

Syntax
------

    sel.selectAllChildren(parentNode)

### Parameters

`parentNode`  
All children of `parentNode` will be selected. `parentNode` itself is not part of the selection.

Example
-------

### HTML

    <main>
      <button>Select Footer</button>
      <p>Welcome to my website.</p>
      <p>I hope you enjoy your visit.</p>
    </main>
    <footer>
      <address>webmaster@example.com</address>
      <p>© 2019</p>
    </footer>

### JavaScript

    const button = document.querySelector('button');
    const footer = document.querySelector('footer');

    button.addEventListener('click', (e) => {
      window.getSelection().selectAllChildren(footer);
    });

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-selectallchildren">Selection API<br />
<span class="small">The definition of 'Selection.selectAllChildren()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current definition</td></tr></tbody></table>

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

`selectAllChildren`

1

12

1

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

See also
--------

-   [`Selection`](../selection), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/selectAllChildren" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/selectAllChildren</a>
