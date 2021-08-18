HTMLSelectElement.remove()
==========================

The `HTMLSelectElement.remove()` method removes the element at the specified index from the options collection for this select element.

Syntax
------

    collection.remove(index);

### Parameters

-   `index` is a long for the index of the [`HTMLOptionElement`](../htmloptionelement) to remove from the collection. If the index is not found the method has no effect.

Example
-------

    var sel = document.getElementById("existingList");
    sel.remove(1);

    /*
      Takes the existing following select object:

      <select id="existingList" name="existingList">
        <option value="1">Option: Value 1</option>
        <option value="2">Option: Value 2</option>
        <option value="3">Option: Value 3</option>
      </select>

      And changes it to:

      <select id="existingList" name="existingList">
        <option value="1">Option: Value 1</option>
        <option value="3">Option: Value 3</option>
      </select>
    */

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-select-remove">HTML Living Standard<br />
<span class="small">The definition of 'HTMLSelectElement.remove()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-select-remove">HTML5<br />
<span class="small">The definition of 'HTMLSelectElement.remove()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Is a snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-33404570">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLSelectElement.remove()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-33404570">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLSelectElement.remove()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`remove`

1

12

1

5.5

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

-   [`ChildNode.remove`](../childnode/remove), the method that gets called when remove is called without arguments on a [`HTMLSelectElement`](../htmlselectelement).
-   [`HTMLSelectElement`](../htmlselectelement) that implements it.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/remove" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/remove</a>
