# HTMLSelectElement.add()

The `HTMLSelectElement.add()` method adds an element to the collection of `option` elements for this `select` element.

## Syntax

    collection.add(item[, before]);

### Parameters

- _item_ is an [`HTMLOptionElement`](../htmloptionelement) or [`HTMLOptGroupElement`](../htmloptgroupelement)
- _before_ is optional and an element of the collection, or an index of type _long_, representing the _item_ should be inserted before. If this parameter is `null` (or the index does not exist), the new element is appended to the end of the collection.

### Exceptions

- A [`DOMError`](../domerror) of the type `HierarchyRequestError` if the _item_ passed to the method is an ancestor of the `HTMLSelectElement`.

## Examples

### Creating Elements from Scratch

    var sel = document.createElement("select");
    var opt1 = document.createElement("option");
    var opt2 = document.createElement("option");

    opt1.value = "1";
    opt1.text = "Option: Value 1";

    opt2.value = "2";
    opt2.text = "Option: Value 2";

    sel.add(opt1, null);
    sel.add(opt2, null);

    /*
      Produces the following, conceptually:

      <select>
        <option value="1">Option: Value 1</option>
        <option value="2">Option: Value 2</option>
      </select>
    */

The before parameter is optional. So the following is accepted.

    ...
    sel.add(opt1);
    sel.add(opt2);
    ...

### Append to an Existing Collection

    var sel = document.getElementById("existingList");

    var opt = document.createElement("option");
    opt.value = "3";
    opt.text = "Option: Value 3";

    sel.add(opt, null);

    /*
      Takes the existing following select object:

      <select id="existingList">
        <option value="1">Option: Value 1</option>
        <option value="2">Option: Value 2</option>
      </select>

      And changes it to:

      <select id="existingList">
        <option value="1">Option: Value 1</option>
        <option value="2">Option: Value 2</option>
        <option value="3">Option: Value 3</option>
      </select>
    */

The before parameter is optional. So the following is accepted.

    ...
    sel.add(opt);
    ...

### Inserting to an Existing Collection

    var sel = document.getElementById("existingList");

    var opt = document.createElement("option");
    opt.value = "3";
    opt.text = "Option: Value 3";

    sel.add(opt, sel.options[1]);

    /*
      Takes the existing following select object:

      <select id="existingList">
        <option value="1">Option: Value 1</option>
        <option value="2">Option: Value 2</option>
      </select>

      And changes it to:

      <select id="existingList">
        <option value="1">Option: Value 1</option>
        <option value="3">Option: Value 3</option>
        <option value="2">Option: Value 2</option>
      </select>
    */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-select-add">HTML Living Standard<br />
<span class="small">The definition of 'HTMLSelectElement.add()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-select-add">HTML5<br />
<span class="small">The definition of 'HTMLSelectElement.add()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Is a snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>.<br />
The value of <code>before</code> can now be a long and is optional. It throws a <a href="../domerror"><code>DOMError</code></a> of the type <code>HierarchyRequestError</code> if the passed <code>item</code> is an ancestor of the <a href="../htmlselectelement"><code>HTMLSelectElement</code></a> and no longer throws if the <code>before</code> parameter is not found.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-14493106">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLSelectElement.add()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The method now throws an NOT_FOUND_ERR exception if the item of the <code>before</code> parameter is not a child of this element.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-14493106">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLSelectElement.add()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`add`

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

`index_before_parameter`

Yes

12

7

Yes

Yes

Yes

Yes

Yes

7

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/add" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/add</a>
