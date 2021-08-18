HTMLSelectElement.selectedIndex
===============================

The `HTMLSelectElement.selectedIndex` is a `long` that reflects the index of the first or last selected [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) element, depending on the value of `multiple`. The value `-1` indicates that no element is selected.

Syntax
------

    var index = selectElem.selectedIndex;
    selectElem.selectedIndex = index;

Example
-------

### HTML

    <p id="p">selectedIndex: 0</p>

    <select id="select">
      <option selected>Option A</option>
      <option>Option B</option>
      <option>Option C</option>
      <option>Option D</option>
      <option>Option E</option>
    </select>

### JavaScript

    var selectElem = document.getElementById('select')
    var pElem = document.getElementById('p')

    // When a new <option> is selected
    selectElem.addEventListener('change', function() {
      var index = selectElem.selectedIndex;
      // Add that data to the <p>
      pElem.innerHTML = 'selectedIndex: ' + index;
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-select-selectedindex">HTML Living Standard<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since the latest snapshot, <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-select-selectedindex">HTML5<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition, snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>.</td></tr></tbody></table>

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

`selectedIndex`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/selectedIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/selectedIndex</a>
