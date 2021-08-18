HTMLSelectElement.namedItem()
=============================

The `HTMLSelectElement.namedItem()` method returns the [`HTMLOptionElement`](../htmloptionelement) corresponding to the [`HTMLOptionElement`](../htmloptionelement) whose `name` or `id` match the specified name, or `null` if no option matches.

In JavaScript, using the array bracket syntax with a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), like `selectElt["value"]` is equivalent to `selectElt``.namedItem("value")`.

Syntax
------

    var item = collection.namedItem(str);
    var item = collection[str];

### Parameters

-   `str` is a [`DOMString`](../domstring).

### Return value

-   `item` is a [`HTMLOptionElement`](../htmloptionelement).

Example
-------

### HTML

    <form>
      <select id="myFormControl">
        <option id="o1">Opt 1</option>
        <option id="o2">Opt 2</option>
      </select>
    </form>

### JavaScript

    elem1 = document.forms[0]['myFormControl']['o1']; // Returns the HTMLOptionElement representing #o1

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-select-nameditem">HTML Living Standard<br />
<span class="small">The definition of 'HTMLSelectElement.namedItem()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since the latest snapshot, <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-select-nameditem">HTML5<br />
<span class="small">The definition of 'HTMLSelectElement.namedItem()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition, snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a></td></tr></tbody></table>

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

`namedItem`

1

12

`namedItem` does not appear to take the `name` attribute into account (only the `id` attribute) on Internet Explorer and Edge. There is a [bug report](https://connect.microsoft.com/IE/feedbackdetail/view/2414092/) to Microsoft about this.

1

6

`namedItem` does not appear to take the `name` attribute into account (only the `id` attribute) on Internet Explorer and Edge. There is a [bug report](https://connect.microsoft.com/IE/feedbackdetail/view/2414092/) to Microsoft about this.

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

-   [`HTMLSelectElement`](../htmlselectelement) that implements it.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/namedItem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/namedItem</a>
