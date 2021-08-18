&lt;datalist&gt;: The HTML Data List element
============================================

The `<datalist>` contains a set of [`<option>`](option) elements that represent the permissible or recommended options available to choose from within other controls.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>Either <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a> or zero or more <a href="option"><code>&lt;option&gt;</code></a> elements.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/listbox_role">listbox</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataListElement"><code>HTMLDataListElement</code></a></td></tr></tbody></table>

Attributes
----------

This element has no other attributes than the [global attributes](../global_attributes), common to all elements.

Examples
--------

### Basic datalist

    <label for="myBrowser">Choose a browser from this list:</label>
    <input list="browsers" id="myBrowser" name="myBrowser" />
    <datalist id="browsers">
      <option value="Chrome">
      <option value="Firefox">
      <option value="Internet Explorer">
      <option value="Opera">
      <option value="Safari">
      <option value="Microsoft Edge">
    </datalist>

#### Result

### Customizing datalist styles

The style of the list produced by a `<datalist>` element is platform-dependent, so if you want to customize the display of the options, you have to implement your own custom solution that overrides the default behavior. The below example provides a simple solution for this. Note how we haven't specified the `<datalist>` `id` inside the `<input>` `list` attribute in this case, as that stops the browser-specific display of the data list items from kicking in. Instead, we are setting the selected `<datalist>` value in the `<input>` via JavaScript.

**Note**: Since `::after` is not permitted on `<input>` elements, if you want to reproduce the arrow-down icon you will have to wrap the `<input>` element in another element that you can hang the styling on (or some other suitable solution).

#### HTML

    <input
      list=""
      name="option"
      id="input"
      autocomplete="off"
    >

    <datalist id="datalist">
      <option>Carrots</option>
      <option>Peas</option>
      <option>Beans</option>
    </datalist>

#### CSS

    datalist {
      position: absolute;
      background-color: lightgrey;
      font-family: sans-serif;
      font-size: 0.8rem;
    }

    option {
      background-color: #bbb;
      padding: 4px;
      margin-bottom: 1px;
      cursor: pointer;
    }

#### JavaScript

    input.onfocus = function () {
      datalist.style.display = 'block';
    }

    input.onblur = function () {
      datalist.style.display = 'none';
    }

    for (let option of datalist.options) {
      option.onclick = function () {
        input.value = this.value;
        datalist.style.display = 'none';
      }
    }

    datalist.style.width = input.offsetWidth + 'px';
    datalist.style.left = input.offsetLeft + 'px';
    datalist.style.top = input.offsetTop + input.offsetHeight + 'px';

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-datalist-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;datalist&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-datalist-element">HTML5<br />
<span class="small">The definition of '&lt;datalist&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`datalist`

20

12

4

10

9.5

12.1

4.4.3

33

4

Since Firefox for Android 79, the dropdown menu containing available options does not appear. See [bug 1535985](https://bugzil.la/1535985).

Yes

The dropdown menu containing available options does not appear in Opera for Android.

12.2

2.0

Polyfill
--------

Include this polyfill to provide support for older and currently incompatible browsers:  
[datalist-polyfill](https://github.com/mfranzke/datalist-polyfill)

See also
--------

-   The [`<input>`](input) element, and more specifically its [`list`](input#attr-list) attribute;
-   The [`<option>`](option) element.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist</a>
