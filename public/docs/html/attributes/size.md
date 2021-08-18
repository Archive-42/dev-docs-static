HTML attribute: size
====================

The `size` attribute defines the width of the [`<input>`](../element/input) and the height of the [`<select>`](../element/select) element. For the `input`, if the `type` attribute is [text](../element/input/text) or [password](../element/input/password) then it's the number of characters. This must be an integer value 0 or higher. If no `size` is specified, or an invalid value is specified, the input has no size declared, and the form control will be the default width based on the user agent. If CSS targets the element with properties impacting the width, CSS takes precedence.

The `size` attribute has no impact on constraint validation.

Examples
--------

By adding `size` on some input types, the width of the input can be controlled. Adding size on a select changes the height, definining how many options are visible in the closed state.

    <label for="fruit">Enter a fruit</label> <input type="text" size="15" id="fruit">
    <label for="vegetable">Enter a vegetable</label> <input type="text" id="vegetable">

    <select name="fruits" size="5">
      <option>banana</option>
      <option>cherry</option>
      <option>strawberry</option>
      <option>durian</option>
      <option>blueberry</option>
    </select>

    <select name="vegetables" size="5">
    <option>carrot</option>
    <option>cucumber</option>
    <option>cauliflower</option>
    <option>celery</option>
    <option>collard greens</option>
    </select>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/input.html#attr-input-size">HTML Living Standard<br />
<span class="small">The definition of 'size attribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/input.html#attr-size-accept">HTML 5.1<br />
<span class="small">The definition of 'size attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `html.elements.attribute.size`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   `maxlength`
-   `minlength`
-   `pattern`

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/size</a>
