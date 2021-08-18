HTMLSelectElement.autofocus
===========================

The `HTMLSelectElement.autofocus` property has a value of either `true` or `false` that reflects the [`autofocus`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-autofocus) HTML attribute, which indicates whether the associated [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element will get input focus when the page loads, unless the user overrides it.

Only one form-associated element in a document can have this attribute specified. If there are several, the first element with the attribute set inserted, usually the first such element on the page, get the initial focus.

Setting this property doesn't set the focus to the associated [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element: it merely tells the browser to focus to it when *the element is inserted* in the document. Setting it after the insertion, that is most of the time after the document load, has no visible effect.

Syntax
------

    aBool = aSelectElement.autofocus; // Get the value of autofocus
    aSelectElement.autofocus = aBool; // Set the value of autofocus

Example
-------

### HTML

    <select id="mySelect" autofocus>
      <option>Option 1</option>
      <option>Option 2</option>
    </select>

### JavaScript

    // Check if the autofocus attribute on the <select>
    var hasAutofocus = document.getElementById('mySelect').autofocus;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-fe-autofocus">HTML Living Standard<br />
<span class="small">The definition of 'autofocus' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#autofocusing-a-form-control-the-autofocus-attribute">HTML 5.2<br />
<span class="small">The definition of 'autofocus' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`autofocus`

1

12

4

10

≤12.1

4

1

18

4

≤12.1

3.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/autofocus" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/autofocus</a>
