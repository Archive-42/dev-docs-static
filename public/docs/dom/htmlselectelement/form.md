HTMLSelectElement.form
======================

The `HTMLSelectElement.form` read-only property returns a [`HTMLFormElement`](../htmlformelement) representing the form that this element is associated with. If the element is not associated with of a [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element, then it returns `null`.

Syntax
------

    aForm = aSelectElement.form.selectname;

Example
-------

### HTML

    <form action="http://www.google.com/search" method="get">
     <label>Google: <input type="search" name="q"></label> <input type="submit" value="Search...">
    </form>

### Javascript

A property available on all form elements, "type" returns the type of the calling form element. For SELECT, the two possible values are "`select-one`" or "`select-multiple`", depending on the type of selection list. The below code gives all SELECT elements in a particular form a CSS class of "`selectclass`":

    <script type="text/javascript">
    var form_element = document.getElementById('subscribe_form');
    var vist = form_element.style;
    if (vist.display=='' || vist.display=='none')
    {
      vist.display = 'block';
    }
    else
    {
      vist.display = 'none';
    }
    </script>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-fae-form">HTML Living Standard<br />
<span class="small">The definition of 'form' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-select-form">HTML5<br />
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

`form`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/form" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/form</a>
