# Option()

The `Option()` constructor creates a new [`HTMLOptionElement`](../htmloptionelement).

## Syntax

    var optionElementReference = new Option(text, value, defaultSelected, selected);

### Parameters

`text` <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) representing the content of the element, i.e. the displayed text. If this is not specified, a default value of "" (empty string) is used.

`value` <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) representing the value of the [`HTMLOptionElement`](../htmloptionelement), i.e. the value attribute of the equivalent [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option). If this is not specified, the value of text is used as the value, e.g. for the associated [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element's value when the form is submitted to the server.

`defaultSelected` <span class="badge inline optional">Optional</span>  
A value of either `true` or `false` that sets the [`selected`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option#attr-selected) attribute value, i.e. so that this [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) will be the default value selected in the [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element when the page is first loaded. If this is not specified, a default value of false is used. Note that a value of true does not set the option to selected if it is not already selected.

`selected` <span class="badge inline optional">Optional</span>  
A value of either `true` or `false` that sets the option's selected state; the default is false (not selected). If omitted, even if the defaultSelected argument is true, the option is not selected.

## Examples

### Just add new options

     /* assuming we have the following HTML
    <select id='s'>

    </select>
    */

    var s = document.getElementById('s');
    var options = [Four, Five, Six];

    options.forEach(function(element,key) {
        s[key] = new Option(element,key);
    });

### Append options with different parameters

    /* assuming we have the following HTML
    <select id="s">
        <option>First</option>
        <option>Second</option>
        <option>Third</option>
    </select>
    */

    var s = document.getElementById('s');
    var options = [ 'zero', 'one', 'two' ];

    options.forEach(function(element, key) {
      if (element == 'zero') {
        s[s.options.length] = new Option(element, s.options.length, false, false);
      }
      if (element == 'one') {
        s[s.options.length] = new Option(element, s.options.length, true, false); // Will add the "selected" attribute
      }
      if (element == 'two') {
        s[s.options.length] = new Option(element, s.options.length, false, true); // Just will be selected in "view"
      }
    });

    /* Result
    <select id="s">
      <option value="0">zero</option>
      <option value="1" selected="">one</option>
      <option value="2">two</option> // User will see this as 'selected'
    </select>
    */

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-option">HTML Living Standard<br />
<span class="small">The definition of 'Option()' in that specification.</span></a></td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement/Option" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement/Option</a>
