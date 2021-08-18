&lt;select&gt;: The HTML Select element
=======================================

The `<select>` represents a control that provides a menu of options:

The above example shows typical `<select>` usage. It is given an `id` attribute to enable it to be associated with a [`<label>`](label) for accessibility purposes, as well as a `name` attribute to represent the name of the associated data point submitted to the server. Each menu option is defined by an [`<option>`](option) element nested inside the `<select>`.

Each `<option>` element should have a [`value`](option#attr-value) attribute containing the data value to submit to the server when that option is selected. If no `value` attribute is included, the value defaults to the text contained inside the element. You can include a [`selected`](../global_attributes#attr-selected) attribute on an `<option>` element to make it selected by default when the page first loads.

The `<select>` element has some unique attributes you can use to control it, such as `multiple` to specify whether multiple options can be selected, and `size` to specify how many options should be shown at once. It also accepts most of the general form input attributes such as `required`, `disabled`, `autofocus`, etc.

You can further nest `<option>` elements inside [`<optgroup>`](optgroup) elements to create separate groups of options inside the dropdown.

For further examples, see [The native form widgets: Drop-down content](https://developer.mozilla.org/en-US/docs/Learn/Forms/Basic_native_form_controls#drop-down_content).

Attributes
----------

This element includes the [global attributes](../global_attributes).

`autocomplete`  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) providing a hint for a [user agent's](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) autocomplete feature. See [The HTML autocomplete attribute](../attributes/autocomplete) for a complete list of values and details on how to use autocomplete.

`autofocus`  
This Boolean attribute lets you specify that a form control should have input focus when the page loads. Only one form element in a document can have the `autofocus` attribute.

`disabled`  
This Boolean attribute indicates that the user cannot interact with the control. If this attribute is not specified, the control inherits its setting from the containing element, for example [`<fieldset>`](fieldset); if there is no containing element with the `disabled` attribute set, then the control is enabled.

`form`  
The [`<form>`](form) element to associate the `<select>` with (its *form owner*). The value of this attribute must be the [`id`](../global_attributes#attr-id) of a `<form>` in the same document. (If this attribute is not set, the `<select>` is associated with its ancestor `<form>` element, if any.)

This attribute lets you associate `<select>` elements to `<form>`s anywhere in the document, not just inside a `<form>`. It can also override an ancestor `<form>` element.

`multiple`  
This Boolean attribute indicates that multiple options can be selected in the list. If it is not specified, then only one option can be selected at a time. When `multiple` is specified, most browsers will show a scrolling list box instead of a single line dropdown.

`name`  
This attribute is used to specify the name of the control.

`required`  
A Boolean attribute indicating that an option with a non-empty string value must be selected.

`size`  
If the control is presented as a scrolling list box (e.g. when `multiple` is specified), this attribute represents the number of rows in the list that should be visible at one time. Browsers are not required to present a select element as a scrolled list box. The default value is `0`.

**Note:** According to the HTML5 specification, the default value for size should be `1`; however, in practice, this has been found to break some web sites, and no other browser currently does that, so Mozilla has opted to continue to return `0` for the time being with Firefox.

Usage notes
-----------

### Selecting multiple options

On a desktop computer, there are a number of ways to select multiple options in a `<select>` element with a `multiple` attribute:

Mouse users can hold the Ctrl, Command, or Shift keys (depending on what makes sense for your operating system) and then click multiple options to select/deselect them.

**Warning**: The mechanism for selecting multiple non-contiguous items via the keyboard described below currently only seems to work in Firefox.

**Also note:** On macOS, the Ctrl + Up and Ctrl + Down shortcuts conflict with the OS default shortcuts for *Mission Control* and *Application windows*, so you'll have to turn these off before it will work.

Keyboard users can select multiple contiguous items by:

-   Focusing on the `<select>` element (e.g. using Tab).
-   Selecting an item at the top or bottom of the range they want to select using the Up and Down cursor keys to go up and down the options.
-   Holding down the Shift key and then using the Up and Down cursor keys to increase or decrease the range of items selected.

Keyboard users can select multiple non-contiguous items by:

-   Focusing on the `<select>` element (e.g. using Tab).
-   Holding down the Ctrl key then using the Up and Down cursor keys to change the "focused" select option, i.e. the one that will be selected if you choose to do so. The "focused" select option is highlighted with a dotted outline, in the same way as a keyboard-focused link.
-   Pressing Space to select/deselect "focused" select options.

Styling with CSS
----------------

The `<select>` element is notoriously difficult to style productively with CSS. You can affect certain aspects like any element — for example, manipulating the [box model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model), the [displayed font](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts), etc., and you can use the [`appearance`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance) property to remove the default system `appearance`.

However, these properties don't produce a consistent result across browsers, and it is hard to do things like line different types of form element up with one another in a column. The `<select>` element's internal structure is complex, and hard to control. If you want to get full control, you should consider using a library with good facilities for styling form widgets, or try rolling your own dropdown menu using non-semantic elements, JavaScript, and [WAI-ARIA](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics) to provide semantics.

For more useful information on styling `<select>`, see:

-   [Styling HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
-   [Advanced styling for HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling)

Also see the "Customizing select styles" example below for an example of you could attempt a simple `<select>` styling.

Examples
--------

### Basic select

The following example creates a very simple dropdown menu, the second option of which is selected by default.

    <!-- The second value will be selected initially -->
    <select name="choice">
      <option value="first">First Value</option>
      <option value="second" selected>Second Value</option>
      <option value="third">Third Value</option>
    </select>

### Advanced select with multiple features

The follow example is more complex, showing off more features you can use on a `<select>` element:

    <label>Please choose one or more pets:
      <select name="pets" multiple size="4">
        <optgroup label="4-legged pets">
          <option value="dog">Dog</option>
          <option value="cat">Cat</option>
          <option value="hamster" disabled>Hamster</option>
        </optgroup>
        <optgroup label="Flying pets">
          <option value="parrot">Parrot</option>
          <option value="macaw">Macaw</option>
          <option value="albatross">Albatross</option>
        </optgroup>
      </select>
    </label>

You'll see that:

-   Multiple options are selectable because we've included the `multiple` attribute.
-   The `size` attribute causes only 4 lines to display at a time; you can scroll to view all the options.
-   We've included [`<optgroup>`](optgroup) elements to divide the options up into different groups. This is a purely visual grouping, its visualization generally consists of the group name being bolded, and the options being indented.
-   The "Hamster" option includes a `disabled` attribute and therefore can't be selected at all.

### Customizing select styles

This example shows how you could use some CSS and JavaScript to provide extensive custom styling for a `<select>` box.

This example basically:

-   Clones the `<select>`'s context (the [`<option>`s](option)) in a parent wrapper and reimplements the standard expected behavior using additional HTML elements and JavaScript. This includes basic tab behavior to provide keyboard accessibility.
-   Maps some standards native `attributes` to `data-attributes` of the new elements in order to manage state and CSS.

Not all native features are supported, it's a Proof of Concept. IT starts from standard HTML but the same results can be achieved starting from JSON data, custom HTML, or other solutions.

#### HTML

    <form>
     <fieldset>
        <legend>Standard controls</legend>
        <select
           name=1A
           id=select
           autocomplete=off
           required
           >
           <option>Carrots</option>
           <option>Peas</option>
           <option>Beans</option>
           <option>Pneumonoultramicroscopicsilicovolcanoconiosis</option>
        </select>
     </fieldset>
     <fieldset id=custom>
        <legend>Custom controls</legend>
        <select
           name="2A"
           id="select"
           autocomplete="off"
           required
           >
           <option>Carrots</option>
           <option>Peas</option>
           <option>Beans</option>
           <option>Pneumonoultramicroscopicsilicovolcanoconiosis</option>
        </select>
      </fieldset>
    </form>

#### CSS

    body {
      font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif
    }

    .select:focus {
      border-color: blue;
    }

    html body form fieldset#custom div.select[data-multiple] div.header {
      display: none;
    }

    html body form fieldset#custom div.select div.header {
      content: '↓';
      display: -webkit-inline-box;
      display: -ms-inline-flexbox;
      display: inline-flex;
      -webkit-box-align: center;
      -ms-flex-align: center;
      align-items: center;
      padding: 0;
      position: relative;
    }

    html body form fieldset#custom div.select div.header::after {
      content: '↓';
      align-self: stretch;
      display: flex;
      align-content: center;
      justify-content: center;
      justify-items: center;
      align-items: center;
      padding: .5em;
    }

    html body form fieldset#custom div.select div.header:hover:after {
      background-color: blue;
    }

    .select .header select {
      -webkit-appearance: none;
      -moz-appearance: none;
      appearance: none;
      font-family: inherit;
      font-size: inherit;
      padding: 0;
      border-width: 0;
      width: 100%;
      flex: 1;
      display: none;
    }

    .select .header select optgroup {
      display: none;
    }

    .select select div.option {
      display: none;
    }

    html body form fieldset#custom div.select {
      user-select: none;
      box-sizing: border-box;
      position: relative;
      border-radius: 4px;
      border-style: solid;
      border-width: 0;
      border-color: gray;
      width: auto;
      display: inline-block;
    }

    html body form fieldset#custom div.select:focus {
      border-color: blue;
    }

    html body form fieldset#custom div.select:hover {
      border-color: blue;
    }

    html body form fieldset#custom div.select[data-open] {
      border-bottom-left-radius: 0;
      border-bottom-right-radius: 0;
    }

    html body form fieldset#custom div.select[data-open] datalist {
      display: initial;
    }

    html body form fieldset#custom div.select datalist {
      -webkit-appearance: none;
      -moz-appearance: none;
      appearance: none;
      position: absolute;
      border-style: solid;
      border-width: 1px;
      border-color: gray;
      left: 0;
      display: none;
      width: 100%;
      box-sizing: border-box;
      z-index: 2;
      border-bottom-left-radius: 4px;
      border-bottom-right-radius: 4px;
    }

    html body form fieldset#custom div.select datalist div.option {
      background-color: white;
      margin-bottom: 1px;
      cursor: pointer;
      padding: 0.5em;
      border-width: 0;
    }

    html body form fieldset#custom div.select datalist div.option:hover {
      background-color: blue;
      color: white;
    }

    html body form fieldset#custom div.select datalist div.option:focus {
      background-color: blue;
      color: white;
    }

    html body form fieldset#custom div.select datalist div.option:checked {
      background-color: blue;
      color: white;
    }

    html body form fieldset#custom div.select div.optgroup div.option[data-disabled] {
      color: gray;
    }

    html body form fieldset#custom div.select div.optgroup div.option[data-checked] {
      background-color: blue;
      color: white;
    }

    html body form fieldset#custom div.select div.optgroup div.label {
      font-weight: bold;
    }

    html body form fieldset#custom div.select div.optgroup div.option div.label {
      font-weight: normal;
      padding: .25em;
    }

    html body form fieldset#custom div.select div.header {
      flex: 1;
      display: flex;
      width: auto;
      box-sizing: border-box;
      border-width: 1px;
      border-style: inherit;
      border-color: inherit;
      border-radius: inherit;
    }

    html body form fieldset#custom div.select div.header span {
      flex: 1;
      padding: .5em;
    }

#### JavaScript

    const selects = custom.querySelectorAll('select');
    for (const select of selects) {
        const div = document.createElement('div');
        const header = document.createElement('div');
        const datalist = document.createElement('datalist');
        const optgroups = select.querySelectorAll('optgroup');
        const span = document.createElement('span');
        const options = select.options;
        const parent = select.parentElement;
        const multiple = select.hasAttribute('multiple');
        const onclick = function(e) {
            const disabled = this.hasAttribute('data-disabled');
            select.value = this.dataset.value;
            span.innerText = this.dataset.label;
            if (disabled) return;
            if (multiple) {
                if (e.shiftKey) {
                    const checked = this.hasAttribute("data-checked");
                    if (checked) {
                        this.removeAttribute("data-checked");
                    } else {
                        this.setAttribute("data-checked", "");
                    };
                } else {
                    const options = div.querySelectorAll('.option');
                    for (i = 0; i < options.length; i++) {
                        const option = options[i];
                        option.removeAttribute("data-checked");
                    };
                    this.setAttribute("data-checked", "");
                };
            };
        };
        const onkeyup = function(e) {
            e.preventDefault();
            e.stopPropagation();
            if (e.keyCode === 13) {
                this.click();
            }
        };
        div.classList.add('select');
        header.classList.add('header');
        div.tabIndex = 1;
        select.tabIndex = -1;
        span.innerText = select.label;
        header.appendChild(span);
        for (attribute of select.attributes) div.dataset[attribute.name] = attribute.value;
        for (i = 0; i < options.length; i++) {
            const option = document.createElement('div');
            const label = document.createElement('div');
            const o = options[i];
            for (attribute of o.attributes) option.dataset[attribute.name] = attribute.value;
            option.classList.add('option');
            label.classList.add('label');
            label.innerText = o.label;
            option.dataset.value = o.value;
            option.dataset.label = o.label;
            option.onclick = onclick;
            option.onkeyup = onkeyup;
            option.tabIndex = i + 1;
            option.appendChild(label);
            datalist.appendChild(option);
        }
        div.appendChild(header);
        for (o of optgroups) {
            const optgroup = document.createElement('div');
            const label = document.createElement('div');
            const options = o.querySelectorAll('option');
            Object.assign(optgroup, o);
            optgroup.classList.add('optgroup');
            label.classList.add('label');
            label.innerText = o.label;
            optgroup.appendChild(label);
            div.appendChild(optgroup);
            for (o of options) {
                const option = document.createElement('div');
                const label = document.createElement('div');
                for (attribute of o.attributes) option.dataset[attribute.name] = attribute.value;
                option.classList.add('option');
                label.classList.add('label');
                label.innerText = o.label;
                option.tabIndex = i + 1;
                option.dataset.value = o.value;
                option.dataset.label = o.label;
                option.onclick = onclick;
                option.onkeyup = onkeyup;
                option.tabIndex = i + 1;
                option.appendChild(label);
                optgroup.appendChild(option);
            };
        };
        div.onclick = function(e) {
            e.preventDefault();
        }
        parent.insertBefore(div, select);
        header.appendChild(select);
        div.appendChild(datalist);
        datalist.style.top = header.offsetTop + header.offsetHeight + 'px';
        div.onclick = function(e) {
            if (multiple) {

            } else {
                const open = this.hasAttribute("data-open");
                e.stopPropagation();
                if (open) {
                    this.removeAttribute("data-open");
                } else {
                    this.setAttribute("data-open", "");
                }
            }
        };
        div.onkeyup = function(event) {
            event.preventDefault();
            if (event.keyCode === 13) {
                this.click();
            }
        };
        document.addEventListener('click', function(e) {
            if (div.hasAttribute("data-open")) div.removeAttribute("data-open");
        });
        const width = Math.max(...Array.from(options).map(function(e) {
            span.innerText = e.label;
            return div.offsetWidth;
        }));
        console.log(width)
        div.style.width = width + 'px';
    }
    document.forms[0].onsubmit = function(e) {
        const data = new FormData(this);
        e.preventDefault();
        submit.innerText = JSON.stringify([...data.entries()]);
    }

#### Result

Technical summary
-----------------

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#interactive_content">interactive content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_listed">listed</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_labelable">labelable</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_resettable">resettable</a>, and <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_submittable">submittable</a> <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form-associated_">form-associated</a> element</td></tr><tr class="even"><td>Permitted content</td><td>Zero or more <a href="option"><code>&lt;option&gt;</code></a> or <a href="optgroup"><code>&lt;optgroup&gt;</code></a> elements.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>combobox</code> with <strong>no</strong> <code>multiple</code> attribute and <strong>no</strong> <code>size</code> attribute greater than 1, otherwise <code>listbox</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>menu</code> with <strong>no</strong> <code>multiple</code> attribute and <strong>no</strong> <code>size</code> attribute greater than 1, otherwise no <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement"><code>HTMLSelectElement</code></a></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-select-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;select&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-select-element">HTML5<br />
<span class="small">The definition of '&lt;select&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/interact/forms.html#h-17.6">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;select&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`select`

Yes

`border-radius` on `<select>` elements is ignored unless `-webkit-appearance` is overridden to an appropriate value.

12

1

Historically, Firefox has allowed keyboard and mouse events to bubble up from the `<option>` element to the parent `<select>` element, although this behavior is inconsistent across many browsers. For better Web compatibility (and for technical reasons), when Firefox is in multi-process mode the `<select>` element is displayed as a drop-down list. The behavior is unchanged if the `<select>` is presented inline and it has either the multiple attribute defined or a size attribute set to more than 1. Rather than watching `<option>` elements for events, you should watch for change events on `<select>`. See [bug 1090602](https://bugzil.la/1090602) for details.

Yes

Yes

Yes

`border-radius` on `<select>` elements is ignored unless `-webkit-appearance` is overridden to an appropriate value.

Yes

\["In the Browser app for Android 4.1 (and possibly later versions), there is a bug where the menu indicator triangle on the side of a `<select>` will not be displayed if a `background`, `border`, or `border-radius` style is applied to the `<select>`.", "`border-radius` on `<select>` elements is ignored unless `-webkit-appearance` is overridden to an appropriate value."\]

Yes

`border-radius` on `<select>` elements is ignored unless `-webkit-appearance` is overridden to an appropriate value.

4

Firefox for Android, by default, sets a `background-image` gradient on all `<select multiple>` elements. This can be disabled using `background-image: none`.

Yes

Yes

`border-radius` on `<select>` elements is ignored unless `-webkit-appearance` is overridden to an appropriate value.

Yes

`border-radius` on `<select>` elements is ignored unless `-webkit-appearance` is overridden to an appropriate value.

`autofocus`

Yes

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`disabled`

Yes

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`form`

Yes

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`multiple`

Yes

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`name`

Yes

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`required`

Yes

12

4

10

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`size`

Yes

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

See also
--------

-   Events fired by `<select>`: [`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event), [`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)
-   The [`<option>`](option) element
-   The [`<optgroup>`](optgroup) element

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select</a>
