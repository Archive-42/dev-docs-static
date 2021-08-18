Selection.addRange()
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.addRange()` method adds a [`Range`](../range) to a [`Selection`](../selection).

Syntax
------

    selection.addRange(range);

### Parameters

`range`  
A [`Range`](../range) object that will be added to the [`Selection`](../selection).

Example
-------

Currently only Firefox supports multiple selection ranges, other browsers will not add new ranges to the selection if it already contains one.

### HTML

    <p>I <strong>insist</strong> that you <strong>try</strong> selecting the <strong>strong words</strong>.</p>
    <button>Select strong words</button>

### JavaScript

    let button = document.querySelector('button');

    button.addEventListener('click', function () {
      let selection = window.getSelection();
      let strongs = document.getElementsByTagName('strong');

      if (selection.rangeCount > 0) {
        selection.removeAllRanges();
      }

      for (let i = 0; i < strongs.length; i++) {
        let range = document.createRange();
        range.selectNode(strongs[i]);
        selection.addRange(range);
      }
    });

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-addrange">Selection API<br />
<span class="small">The definition of 'Selection.addRange()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`addRange`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   [`Selection`](../selection), the interface this method belongs to

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/addRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/addRange</a>
